# pandemic-words

<html>
    <head>
        <meta charset="utf-8">
        <link rel="stylesheet" href="./style.css" type="text/css" media="screen">
    </head>
    <body>
        
        <h1>One-column layout</h1>
    
        <p><a href="../viewer.html?one-column">View source code</a><p>
        
        <div class="parent">
            <div class="narrative">
                <div class="narrative-item">
                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                </div>
                <div class="narrative-item">
                     Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                 </div>
                 <div class="narrative-item">
                     Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
                 </div>
                 <div class="narrative-item">
                     Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                 </div>
            </div>
            <div class="sticky-outer">
                <div class="chart"></div>
            </div>
        </div>

        <script src="//cdnjs.cloudflare.com/ajax/libs/waypoints/4.0.1/noframework.waypoints.min.js"></script>
        <script src="//code.jquery.com/jquery-latest.min.js"></script>
        <script src="//cdnjs.cloudflare.com/ajax/libs/fixto/0.5.0/fixto.min.js"></script>
        <script src="../../dist/two-step.js" type="text/javascript" charset="utf-8"></script>

        <script src="./script.js" type="text/javascript" charset="utf-8"></script>
        
    </body>
</html>

body {
    margin-bottom: 200vh;
}
.parent {
    position: relative;
}
.narrative {

}
.narrative-item {
    width: 300px;
    display: block;
    margin: 0 auto;
    margin-top: 80vh;
    color: #ccc;
    transition: color 200ms;
}
.narrative-item.active {
    background: rgba(0, 0, 0, 0.1);
    color: black;
}
.sticky-outer {
    position: absolute;
    height: calc(100% + 200vh);
    width: 100%;
    top: -80vh;
    left: 0;
    z-index: -1;
}

.chart {
    width: 100%;
    height: 100vh;
    background: rgb(228, 228, 228);
    padding: 100px;
    box-sizing: border-box;
    text-align: center;
    font-size: 30px;
}

var ts = new TwoStep({
    elements: document.querySelectorAll('.parent .narrative-item'),
    onChange: function(event) {
        console.log('Item '+event.index);
    },
    stick: document.querySelector('.parent .sticky-outer'),
    narrative: [
        function(event) {
            $('.parent .chart').text('Item '+event.index);
        },
        function(event) {
            $('.parent .chart').text('Item '+event.index);
        },
        function(event) {
            $('.parent .chart').text('Item '+event.index);
        },
        function(event) {
            $('.parent .chart').text('Item '+event.index);
        }
    ],
    offset: {
        up: '-10%',
        down: '100%'
    }
});
