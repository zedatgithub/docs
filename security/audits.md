# 📕 Audits

### Audits

* [ ] [https://rugdoc.io/​](https://rugdoc.io/) \( had initial talking they suggested audit from paladinsec but we had to postpone that audit because being too expensive "Starting from 6k to 40k+++"  \)
* [ ] [https://techrate.org/](https://techrate.org/) \( contacted \)
* [ ] [https://mythx.io/](https://mythx.io/) \( signed up \)
* [ ] [https://paladinsec.co/](https://paladinsec.co/audits/#contact) or [https://www.certik.org/](https://www.certik.org/)  \(one of them after 2 week of launch and will be paid from [Fee/Tax Distribution](../features/deposit-fee-redistribution.md) \)

MasterChef contract, forked from Pancake v1 Certik audited project.  
AMM contracts, forked from Pancakeswap v1 Certik audited project.

BSC Online Contract Checker[ ](https://galaxyfinance.one/contractdiffchecker.html?a1=0xBCfCcbde45cE874adCB698cC183deBcF17952812&a2=0xd7581640DBfC558b3f4d729B8f8c60e0122511F8)\( feel free to compare different contracts \)

* [PacakeFactory vs DXAMMFactory](https://galaxyfinance.one/contractdiffchecker.html?a1=0xBCfCcbde45cE874adCB698cC183deBcF17952812&a2=0xd7581640DBfC558b3f4d729B8f8c60e0122511F8) 
* [PacakeRouter vs DXAMMRouter](https://galaxyfinance.one/contractdiffchecker.html?a1=0x05ff2b0db69458a0750badebc4f9e13add608c7f&a2=0x3d492a1Cf02112f201721544e13a5e239a5258d9) 

_\* this small JavaScript tool downloads the smart contracts' source code from_ [_https://api.bscscan.com_](https://api.bscscan.com) _and compares it_  
  
Binance Smart Chain - Online Contract Diff Checker source code which runs on your PC instead on server

```javascript
<script src="https://cdnjs.cloudflare.com/ajax/libs/jsdiff/5.0.0/diff.min.js" integrity="sha512-Rjml7/E2zETyVFhzIQnTEjW7PBCH5/Y4ac2uu9MGqh1JclCVHbvT1lIlcVmvAGFipi/L16eA6Jr9km2zit9Tfg==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
<title>Binance Smart Chain - Online Contract Checker</title>
<pre id="display"></pre>
<script>
    urlParams = new URLSearchParams(window.location.search);
    function getFlatSourceCode(address) {
        var xmlHttp = new XMLHttpRequest();
        xmlHttp.open( "GET", 'https://api.bscscan.com/api?module=contract&action=getsourcecode&apikey=E1GZ8ZJZ1G2KC314EPJQQIP8MCAG9X553D&address=' + address, false );
        xmlHttp.send( null );
        response = JSON.parse(xmlHttp.responseText)
        sourceCode = response.result[0].SourceCode;
        if (undefined === sourceCode) return 'Address ' + address + ' ' + (undefined === response.result ? 'Failed to get sourcecode' : response.result) + '<br>';
        if (sourceCode.substring(0, 2) == '{{') {
            sourceCodes = JSON.parse(sourceCode.substring(1, sourceCode.length-1)).sources;
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
        return sourceCode.replace(/\n/g, '\n<br>');
    }
    var diff = Diff.diffLines(getFlatSourceCode(urlParams.get('a1')), getFlatSourceCode(urlParams.get('a2')), {ignoreWhitespace: true, newlineIsToken: true}),
        display = document.getElementById('display'),
        fragment = document.createDocumentFragment();
    diff.forEach(function(part){
        color = part.added ? 'green' : part.removed ? 'red' : 'grey';
        span = document.createElement('span');
        span.style.color = color;
        span.appendChild(document.createTextNode(part.value.replace(/<br>/g, '\n')));
        fragment.appendChild(span);
    });
    display.appendChild(fragment);
</script>
```

  
      


