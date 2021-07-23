# 📕 Audits

### Audits

* [ ] [https://rugdoc.io/​](https://rugdoc.io/) \( held initial talks and they suggested audit from paladinsec but we had to postpone that audit because of being too expensive "Starting from 6k to 40k+++"  \)
* [ ] [https://techrate.org/](https://techrate.org/) \( contacted \)
* [ ] [https://mythx.io/](https://mythx.io/) \( signed up \)
* [ ] [https://paladinsec.co/](https://paladinsec.co/audits/#contact) or [https://www.certik.org/](https://www.certik.org/)  \(we will do one of them 2 weeks after the launch and will be paid from [Fee/Tax Distribution](../features/deposit-fee-redistribution.md)\)

MasterChef contract, forked from Pancake v1 Certik audited project.  
AMM contracts, forked from Pancakeswap v1 Certik audited project.

Online Contract diff-checker[ ](https://galaxyfinance.one/contractdiffchecker.html?a1=0xBCfCcbde45cE874adCB698cC183deBcF17952812&a2=0xd7581640DBfC558b3f4d729B8f8c60e0122511F8)\( feel free to compare other contracts, too \)

* [PancakeFactory vs DXAMMFactory](https://galaxyfinance.one/contractdiffchecker.html?a1=0xBCfCcbde45cE874adCB698cC183deBcF17952812&a2=0xd7581640DBfC558b3f4d729B8f8c60e0122511F8) 
* [PancakeRouter vs DXAMMRouter](https://galaxyfinance.one/contractdiffchecker.html?a1=0x05ff2b0db69458a0750badebc4f9e13add608c7f&a2=0x3d492a1Cf02112f201721544e13a5e239a5258d9) 

_\* this small JavaScript tool downloads the 2 smart contract source codes from_ [_https://api.bscscan.com_](https://api.bscscan.com) _and compares it_  
  
Binance Smart Chain - Online Contract Diff Checker source code which runs on your PC instead on server

```javascript
<!DOCTYPE html>
<html lang="en-us">
    <head>
    <meta charset="utf-8" />
    <link rel="stylesheet" type="text/css" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/10.7.1/styles/github.min.css" />
    <link rel="stylesheet" type="text/css" href="https://cdn.jsdelivr.net/npm/diff2html/bundles/css/diff2html.min.css" />
    <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/diff2html/bundles/js/diff2html-ui.min.js"></script>
    <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/jsdiff/5.0.0/diff.min.js"></script>
    <title>Binance Smart Chain - Online Contract Diff Checker</title>
</head>
<script>
    urlParams = new URLSearchParams(window.location.search);
    function getFlatSourceCode(address) {
        var xmlHttp = new XMLHttpRequest();
        xmlHttp.open("GET", 'https://zed.ro/apiXmodule=contract&action=getsourcecode&apikey=E1GZ8ZJZ1G2KC314EPJQQIP8MCAG9X553D&address=' + address, false);
        xmlHttp.send(null);
        response = JSON.parse(xmlHttp.responseText)
        sourceCode = response.result[0].SourceCode;
        if (undefined === sourceCode) return 'Address ' + address + ' ' + (undefined === response.result ? 'Failed to get sourcecode' : response.result) + '<br>';
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
        if (urlParams.get('ignore')) urlParams.get('ignore').split(',').map(function (e) { sourceCode = sourceCode.replace(new RegExp(e, 'g'), ''); })
        return sourceCode.replace(/\r+/g, '\n').replace(/\n{2,}/g, '\n').trim();
    }
    diffString = Diff.createTwoFilesPatch(urlParams.get('a1'), urlParams.get('a2'), getFlatSourceCode(urlParams.get('a1')), getFlatSourceCode(urlParams.get('a2')));
    document.addEventListener('DOMContentLoaded', function () {
        var targetElement = document.getElementById('myDiffElement');
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
    <div id="myDiffElement"></div>
</body>
</html>
```

  
      


