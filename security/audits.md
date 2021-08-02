# 📕 Audits

## Audits

* [ ] [BCFC.io](https://bcfg.io/) are the first ones to have done an audit for us, on **July 31st, 2021**; the [PDF document is posted on their GitHub account](https://github.com/BCFG-Audit/Smart_Contract_Security_Audits/blob/main/GalaxyFinance_BCFG_AUDIT.pdf) and also available for [download from our website](https://galaxyfinance.one/GalaxyFinance_BCFG_AUDIT.pdf)
* [ ] [https://rugdoc.io/​](https://rugdoc.io/) \( held initial talks and they suggested audit from paladinsec but we had to postpone that audit because of being too expensive "Starting from 6k to 40k+++"  \)
* [ ] [https://techrate.org/](https://techrate.org/) \( contacted \)
* [ ] [https://mythx.io/](https://mythx.io/) \( signed up \)
* [ ] [https://paladinsec.co/](https://paladinsec.co/audits/#contact) or [https://www.certik.org/](https://www.certik.org/)  \(we will do one of them 2 weeks after the launch and will be paid from [Fee/Tax Distribution](../features/deposit-fee-redistribution.md)\)

MasterChef contract, forked from Pancake v1 Certik audited project.  
AMM contracts, forked from Pancakeswap v1 Certik audited project.

Online multi-chain smart contract diff checker[ ](https://galaxyfinance.one/contractdiffchecker.html?a1=0xBCfCcbde45cE874adCB698cC183deBcF17952812&a2=0xd7581640DBfC558b3f4d729B8f8c60e0122511F8)\( feel free to compare different contracts \)

* [PancakeFactory vs DXAMMFactory](https://galaxyfinance.one/contractdiffchecker.html?ignore=Pancake%2Cpancake%2CCake%2CGalaxy%2Cpragma+solidity.*&chain1=Binance&address1=0xBCfCcbde45cE874adCB698cC183deBcF17952812&chain2=Binance&address2=0xd7581640DBfC558b3f4d729B8f8c60e0122511F8) 
* [PancakeRouter vs DXAMMRouter](https://galaxyfinance.one/contractdiffchecker.html?ignore=Pancake%2CGalaxy%2Cpragma+solidity.*&chain1=Binance&address1=0x05ff2b0db69458a0750badebc4f9e13add608c7f&chain2=Binance&address2=0x3d492a1Cf02112f201721544e13a5e239a5258d9) 

_\* this small JavaScript tool downloads the 2 smart contract source codes from_ [_https://api.bscscan.com_](https://api.bscscan.com)_,_ [_https://api.hecoinfo.com_](https://api.hecoinfo.com)_,_ [_https://api.polygon.com_](https://api.polygon.com)_,_ [_https://api.ftmscan.com/_](https://api.ftmscan.com/) _and compares it on your PC_

Online multi-chain smart contract diff checker source code which runs on your PC instead on any server

```javascript
<!DOCTYPE html>
<html lang="en-us">
<head>
    <meta charset="utf-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="shortcut icon" href="favicon.png" />
    <link rel="stylesheet" type="text/css" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/10.7.1/styles/github.min.css" />
    <link rel="stylesheet" type="text/css" href="https://cdn.jsdelivr.net/npm/diff2html/bundles/css/diff2html.min.css" />
    <link rel="stylesheet" type="text/css" href="https://cdn.jsdelivr.net/npm/bootstrap@3.4.1/dist/css/bootstrap.min.css" />
    <link rel="stylesheet" type="text/css" href="https://cdn.jsdelivr.net/npm/bootswatch@3.4.1/flatly/bootstrap.min.css" />
    <link rel="stylesheet" type="text/css" href="https://cdn.jsdelivr.net/npm/font-awesome@4.7.0/css/font-awesome.min.css" />
    <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/diff2html/bundles/js/diff2html-ui.min.js"></script>
    <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/jquery@3.6.0/dist/jquery.min.js"></script>
    <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/bootstrap@3.4.1/dist/js/bootstrap.min.js"></script>
    <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/diff@5.0.0/dist/diff.min.js"></script>
    <title>GalaxyFinance.One - Online multi-chain smart contract diff checker</title>
    <style>
        body {
            margin: 0;
            padding: 0;
        }
        a {
            text-decoration: none;
        }
        .navbar {
            margin-bottom: 10px;
        }
        .navbar-header img {
            float: left;
            position: relative;
            top: -14px;
            margin-right: 20px;
        }
        .row-no-gutters .input-group-addon {
            padding: 1px;
        }
        .row-no-gutters .input-group-addon select.form-control {
            width: 110px;
            height: auto;
            padding-top: 7px;
            padding-bottom: 7px;
        }
        .row-no-gutters .col-sm-2 {
            padding-left: 10px;
            padding-right: 10px;
        }
        #loading-img{
            background:url(https://cdnjs.cloudflare.com/ajax/libs/bxslider/4.2.5/images/bx_loader.gif) center center no-repeat;
            height: 100%;
            z-index: 4;
        }
        .overlay{
            background: #e9e9e9;
            position: absolute;
            top: 0;
            right: 0;
            bottom: 0;
            left: 0;
            opacity: .7;
            z-index: 3;
        }
        .pointer {
            cursor: pointer;
        }
        .mb0 {
            margin-bottom: 0;
        }
        @media (max-width: 767px) {
            .row-no-gutters .col-sm-2 {
                padding-left: 0;
                padding-right: 0;
            }
        }
    </style>
    <script>
    $(document).ready(function () {
        var urlParams = new URLSearchParams(window.location.search), diffString = '', diff2htmlUi;
        $("#address1").val(urlParams.get('address1'));
        $("#address2").val(urlParams.get('address2'));
        $("#chain1").val(urlParams.get('chain1') ? urlParams.get('chain1') : 'Binance');
        $("#chain2").val(urlParams.get('chain2') ? urlParams.get('chain2') : 'Binance');
        $("#ignore").val(urlParams.get('ignore'));
        $("#ignore_ignored").prop('checked', urlParams.get('ignore_ignored'));
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
                if (urlParams.get('ignore') && !urlParams.get('ignore_ignored')) urlParams.get('ignore').split(',').map(function (e) { sourceCode = sourceCode.replace(new RegExp(e.trim(), 'gm'), ''); })
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
        if (contract1.source && contract2.source) {
            diff2htmlUi = new Diff2HtmlUI(targetElement, diffString, configuration);
            diff2htmlUi.draw();
            diff2htmlUi.highlightCode();
        } else $('#alert').removeClass('hidden');
        $('[data-toggle="popover"]').popover();
    });
    </script>
</head>
<body>
    <div class="overlay"><div id="loading-img"></div></div>
    <nav class="navbar navbar-default">
        <div class="container-fluid">
            <div class="navbar-header">
                <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#navbar-collapse" aria-expanded="false">
                    <span class="sr-only">Toggle navigation</span>
                    <span class="icon-bar"></span>
                    <span class="icon-bar"></span>
                    <span class="icon-bar"></span>
                </button>
                <a class="navbar-brand" href="https://galaxyfinance.one/"><img alt="Brand" src="logo-inverted.png" width="48"><span class="hidden-xs">GalaxyFinance.One &nbsp;&nbsp;&raquo;&nbsp;&nbsp; Online multi-chain smart contract diff checker</span></a>
            </div>
            <div class="collapse navbar-collapse" id="navbar-collapse">
                <ul class="nav navbar-nav navbar-right">
                    <li class="dropdown">
                        <a href="#" class="dropdown-toggle" data-toggle="dropdown" role="button" aria-haspopup="true" aria-expanded="false">Examples <span class="caret"></span></a>
                        <ul class="dropdown-menu">
                            <li><a href="?ignore=Pancake%2C+pancake%2C+Cake%2C+Galaxy%2C+pragma+solidity.*&chain1=Binance&address1=0xBCfCcbde45cE874adCB698cC183deBcF17952812&chain2=Binance&address2=0xd7581640DBfC558b3f4d729B8f8c60e0122511F8">PancakeFactory vs GalaxyFactory</a></li>
                            <li><a href="?ignore=Pancake%2CGalaxy%2Cpragma+solidity.*&chain1=Binance&address1=0x05ff2b0db69458a0750badebc4f9e13add608c7f&chain2=Binance&address2=0x3d492a1Cf02112f201721544e13a5e239a5258d9">PancakeRouter vs GalaxyRouter</a></li>
                        </ul>
                    </li>
                </ul>
            </div>
        </div>
    </nav>
    <div class="container-fluid">
        <div class="row">
            <div class="col-xs-12">
                <form action="" method="get">
                    <div class="form-group">
                        <label>Comma separated list of words to ignore (case sensitive) <a href="javascript: void(0)" data-toggle="popover" data-html="true" data-placement="auto" data-trigger="focus" title="Ignoring words" data-content="When comparing contracts you will often find yourself stumbling upon things that should not be considered as differences like, for example, when comparing a token's contract against Pancake's token contracts you will notice instances of <strong>IPancakeERC20</strong> being compared to instances of <strong>IOtherTokenERC20</strong>. In this case, you'd want to ignore all instances of <strong>Pancake</strong> and <strong>OtherToken</strong> making it a lot easier to see what the real difference is between the two contracts."> &nbsp;<i class="fa fa-question-circle"></i></a></label>
                        <div class="input-group">
                            <input type="text" id="ignore" name="ignore" class="form-control" placeholder="Values to ignore">
                            <span class="input-group-addon">
                                <input type="checkbox" name="ignore_ignored" id="ignore_ignored" value="1"> &nbsp;<label for="ignore_ignored" class="mb0 pointer">Show without</label> <a href="javascript: void(0)" data-toggle="popover" data-html="true" data-placement="auto" data-trigger="focus" title="Show without ignoring words" data-content="Tick the checkbox to have the comparison done without applying the ignore words."> &nbsp;<i class="fa fa-question-circle"></i></a>
                            </span>
                        </div>
                    </div>
                    <div class="form-group">
                        <div class="row row-no-gutters">
                            <div class="col-sm-5">
                                <div class="input-group">
                                    <span class="input-group-addon">
                                        <select id="chain1" name="chain1" class="form-control">
                                            <option>Binance</option>
                                            <option>Heco</option>
                                            <option>Polygon</option>
                                            <option>Fantom</option>
                                        </select>
                                    </span>
                                    <input type="text" id="address1" name="address1" placeholder="Smart contract address" class="form-control">
                                </div>
                            </div>
                            <div class="col-sm-5 col-sm-push-2">
                                <div class="input-group">
                                    <span class="input-group-addon">
                                        <select id="chain2" name="chain2" class="form-control">
                                            <option>Binance</option>
                                            <option>Heco</option>
                                            <option>Polygon</option>
                                            <option>Fantom</option>
                                        </select>
                                    </span>
                                    <input type="text" id="address2" name="address2" placeholder="Smart contract address" class="form-control">
                                </div>
                            </div>
                            <div class="col-sm-2 col-sm-pull-5">
                                <input type="submit" id="compare" value="Compare" onclick="$('.overlay').show();" class="btn btn-primary btn-block">
                            </div>
                        </div>
                    </div>
                </form>
                <div id="diffResult">
                    <div id="alert" class="alert alert-info text-center hidden" role="alert">Unable to compare. Make sure you have <strong>correct networks</strong> selected and that the <strong>smart contract addresses</strong> are correct.</div>
                </div>
            </div>
        </div>
    </div>
</body>
</html>
```

