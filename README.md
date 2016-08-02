# proxmox-graphics

Library for creating Canvas Graphics from RRD data.

It feeds from proxmox API RRD data.


## How to use

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
    
    <script type="text/javascript">
        vGraphics({
            id: 100,
            label: 'CPU',
            type: 'cpu',
            element: 'myChart'
        });
        vGraphics({
            id: 100,
            label: 'Net',
            type: 'net',
            element: 'myChart2'
        });
        vGraphics({
            id: 100,
            label: 'Disk',
            type: 'disk',
            element: 'myChart3'
        });
        vGraphics({
            id: 100,
            label: 'Memory',
            type: 'memory',
            element: 'myChart4'
        });
    </script>
