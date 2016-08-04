# proxmox-graphics


Library for creating Canvas Graphics from RRD data.
It feeds from proxmox API RRD data.

## Requierements
 * Proxmox API -> https://github.com/kidandcat/proxmox-rest-api

## How to use

        <!DOCTYPE html>
        <html>
        
        <head>
            <meta charset="utf-8">
            <title></title>
            <script src="vGraphics.js" charset="utf-8"></script>
            <style media="screen">
                .main {
                    width: 50%;
                    height: 50%;
                }
        
                .container {
                    display: flex;
                }
        
                div {
                    flex: 1;
                }
            </style>
        </head>
        
        <body>
            <select onchange="regraphic(this)">
                <option value="" disabled selected style="display:none;">Label</option>
                <option value="100">100</option>
                <option value="101">101</option>
                <option value="102">102</option>
                <option value="103">103</option>
                <option value="104">104</option>
                <option value="105">105</option>
            </select>
            <div class="main">
                <div class="container">
                    <div>
                        <canvas id="myChart" width="200" height="100"></canvas>
                    </div>
                    <div>
                        <canvas id="myChart2" width="200" height="100"></canvas>
                    </div>
                </div>
                <div class="container">
                    <div>
                        <canvas id="myChart3" width="200" height="100"></canvas>
                    </div>
                    <div>
                        <canvas id="myChart4" width="200" height="100"></canvas>
                    </div>
                </div>
            </div>
        
        
            <script type="text/javascript">
                var v1, v2, v3, v4;
        
                function kill() {
                    try {
                        v1.kill();
                        v2.kill();
                        v3.kill();
                        v4.kill();
                    } catch (e) {}
                }
        
                function regraphic(elem) {
                    var id = elem.value || elem;
                    kill();
        
                    try {
                        v1 = vGraphics({
                            id: id,
                            label: 'CPU %',
                            type: 'cpu',
                            element: 'myChart',
                            max: 100
                        });
                        v2 = vGraphics({
                            id: id,
                            label: 'Net KB/s',
                            type: 'net',
                            element: 'myChart2'
                        });
                        v3 = vGraphics({
                            id: id,
                            label: 'Disk GB',
                            type: 'disk',
                            element: 'myChart3'
                        });
                        v4 = vGraphics({
                            id: id,
                            label: 'Memory MB',
                            type: 'memory',
                            element: 'myChart4'
                        });
        
        
                    } catch (e) {}
        
        
                }
            </script>
        </body>
        
        </html>
