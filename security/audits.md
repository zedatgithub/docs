# 📕 Audits

### Audits

* [ ] [https://rugdoc.io/​](https://rugdoc.io/) \( held initial talks and they suggested audit from paladinsec but we had to postpone that audit because of being too expensive "Starting from 6k to 40k+++"  \)
* [ ] [https://techrate.org/](https://techrate.org/) \( contacted \)
* [ ] [https://mythx.io/](https://mythx.io/) \( signed up \)
* [ ] [https://paladinsec.co/](https://paladinsec.co/audits/#contact) or [https://www.certik.org/](https://www.certik.org/)  \(we will do one of them 2 weeks after the launch and will be paid from [Fee/Tax Distribution](../features/deposit-fee-redistribution.md)\)

MasterChef contract, forked from Pancake v1 Certik audited project.  
AMM contracts, forked from Pancakeswap v1 Certik audited project.

You can compare our own Factory and Router contracts with those of PancakeSwap using our online multi-chain smart contract diff checker\*:

* [PancakeFactory vs DXAMMFactory](https://galaxyfinance.one/contractdiffchecker.html?ignore=Pancake%2Cpancake%2CCake%2CGalaxy%2Cpragma+solidity.*&chain1=Binance&address1=0xBCfCcbde45cE874adCB698cC183deBcF17952812&chain2=Binance&address2=0xd7581640DBfC558b3f4d729B8f8c60e0122511F8) 
* [PancakeRouter vs DXAMMRouter](https://galaxyfinance.one/contractdiffchecker.html?ignore=Pancake%2CGalaxy%2Cpragma+solidity.*&chain1=Binance&address1=0x05ff2b0db69458a0750badebc4f9e13add608c7f&chain2=Binance&address2=0x3d492a1Cf02112f201721544e13a5e239a5258d9) 

_\* this is a small JavaScript tool that downloads the source codes of the specified smart contracts from the selected blockchain \(_[_https://api.bscscan.com_](https://api.bscscan.com)_,_ [_https://api.hecoinfo.com_](https://api.hecoinfo.com)_,_ [_https://api.polygon.com_](https://api.polygon.com)_,_ [_https://api.ftmscan.com/_](https://api.ftmscan.com/)_\) and compares them for you. This is a tool that runs locally, on your machine, and for which you can find the source code below:_

```javascript
<!DOCTYPE html>
<html lang="en-us">
<head>
    <meta charset="utf-8" />
    <link rel="stylesheet" type="text/css" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/10.7.1/styles/github.min.css" />
    <link rel="stylesheet" type="text/css" href="https://cdn.jsdelivr.net/npm/diff2html/bundles/css/diff2html.min.css" />
    <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/diff2html/bundles/js/diff2html-ui.min.js"></script>
    <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/jquery@3.6.0/dist/jquery.min.js"></script>
    <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/diff@5.0.0/dist/diff.min.js"></script>
    <title>Multi Chain - Online Contract Checker</title>
    <style>body{margin:0;padding:0}input,select{border:1px solid #ccc;font-size:17px;padding:.5em;margin:.1em}#disabled{width:260px}#ignore{width:75%}#address1,#address2{width:35%}#verify{width:70px}#diffResult{clear:both;margin:.1em}#loading-img{background:url(http://preloaders.net/preloaders/360/Velocity.gif) center center no-repeat;height:100%;z-index:20}.overlay{background:#e9e9e9;display:none;position:absolute;top:0;right:0;bottom:0;left:0;opacity:.5}</style>
</head>
<script>
    $(document).ready(function () {
        urlParams = new URLSearchParams(window.location.search);
        $("#address1").val(urlParams.get('address1'));
        $("#address2").val(urlParams.get('address2'));
        $("#chain1").val(urlParams.get('chain1') ? urlParams.get('chain1') : 'Binance');
        $("#chain2").val(urlParams.get('chain2') ? urlParams.get('chain2') : 'Binance');
        $("#ignore").val(urlParams.get('ignore'));
        function getFlatSourceCode(address, chain) {
            if (!/^(0x)?[0-9a-f]{40}$/i.test(address)) return { name: '', source: 'Invalid address: ' + address};
            if (chain == 'Heco') url = 'https://api.hecoinfo.com/api?module=contract&action=getsourcecode&apikey=5G3VJVUHVXCHY4JB1VECKYUMMPZCMXVZH6&address=';
            else if (chain == 'Polygon') url = 'https://api.polygonscan.com/api?module=contract&action=getsourcecode&apikey=WJXAMUTNMUV98I5NQPYM4URY2YK9RIBW25&address=';
            else if (chain == 'Fantom') url = 'https://api.ftmscan.com/api?module=contract&action=getsourcecode&apikey=H78J721C8UY75RIRJPZZ9BXMFJ2J15E2G9&address=';
            else url = 'https://api.bscscan.com/api?module=contract&action=getsourcecode&apikey=E1GZ8ZJZ1G2KC314EPJQQIP8MCAG9X553D&address=';
            try {
                var xmlHttp = new XMLHttpRequest();
                xmlHttp.open("GET", url + address, false);
                xmlHttp.send(null);
                response = JSON.parse(xmlHttp.responseText)
                sourceCode = response.result[0].SourceCode;
                if (undefined === sourceCode) return { name: '', source: 'Address ' + address + ' ' + (undefined === response.result ? 'Failed to get sourcecode' : response.result)};
                if (sourceCode.substring(0, 2) == '{{') {
                    sourceCodes = JSON.parse(sourceCode.substring(1, sourceCode.length - 1)).sources;
                    sourceCode = '';
                    func = {}
                    loop = 0;
                    Object.keys(sourceCodes).forEach((k) => { func[k.match(/[^\/]*.sol/).pop()] = sourceCodes[k].content.replace(/\n/g, '\n'); })
                    do {
                        hasImports = false;
                        Object.keys(func).forEach((a) => {
                            if (imports = func[a].match(/import(.*);/gm)) {
                                hasImports = true;
                                for (k in imports) {
                                    key = imports[k].match(/[^\/]*.sol/).pop();
                                    func[a] = func[a].replace(imports[k], func[key])
                                    func[key] = '';
                                }
                            }
                        });
                    } while (hasImports && loop++ < 100)
                    Object.keys(func).forEach((k) => { if (func[k]) sourceCode = func[k]; })
                }
                if (urlParams.get('ignore')) urlParams.get('ignore').split(',').map(function (e) { sourceCode = sourceCode.replace(new RegExp(e, 'gm'), ''); })
            } catch (e) {
                return { name: '', source: 'Address ' + address + ' failed to get sourcecode.' + e};
            }
            return { name: response.result[0].ContractName, source: sourceCode.replace(/\r+/g, '\n').replace(/\n{2,}/g, '\n').trim() };
        }
        $(".overlay").show();
        if (urlParams.get('address1')) contract1 = getFlatSourceCode(urlParams.get('address1'), urlParams.get('chain1'));
        if (urlParams.get('address2')) contract2 = getFlatSourceCode(urlParams.get('address2'), urlParams.get('chain2'));
        if (urlParams.get('address1') && urlParams.get('address2')) diffString = Diff.createTwoFilesPatch(contract1.name, contract2.name, contract1.source, contract2.source);
        $(".overlay").hide();
        var targetElement = document.getElementById('diffResult');
        var configuration = {
            drawFileList: false,
            fileListToggle: false,
            fileContentToggle: false,
            outputFormat: 'side-by-side',
        };
        var diff2htmlUi = new Diff2HtmlUI(targetElement, diffString, configuration);
        diff2htmlUi.draw();
        diff2htmlUi.highlightCode();
    });
</script>
<body>
    <div class="overlay">
        <div id="loading-img"></div>
    </div>
    <form action='' method='get'>
        <div>
            <input type='text' id='disabled' value='Comma separated ignored words' disabled>
            <input type='text' id='ignore' name='ignore' title='Comma separated ignored words' placeholder='Comma separated ignored words'>
        </div>
        <div>
            <select id='chain1' name='chain1'>
                <option>Binance</option>
                <option>Heco</option>
                <option>Polygon</option>
                <option>Fantom</option>
            </select>
            <input type='text' id='address1' name='address1' title='Smart contract address' placeholder='Smart contract address'>
            <input type='submit' id='verify' value='Verify' onclick='$(".overlay").show();'>
            <select id='chain2' name='chain2'>
                <option>Binance</option>
                <option>Heco</option>
                <option>Polygon</option>
                <option>Fantom</option>
            </select>
            <input type='text' id='address2' name='address2' title='Smart contract address' placeholder='Smart contract address'>
        </div>
    </form>
    <div id="diffResult"></div>
</body>
</html>
```

  
      


