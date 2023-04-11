<div class="menu {$$props.class}">
    <ul class="option-list">
        <li>
            Option 1
        </li>
        <li>
            Option 2
        </li>
        <li>
            Option 3
        </li>
        <li>
            Option 3
        </li>
        <li>
            Option 3
        </li>
        <li>
            Option 3
        </li>
        <li>
            Option 3
        </li>
    </ul>
</div>
<style>
    .menu:hover{
        display: block !important;
    }
    .menu{
        position: absolute;
        top: 54px;
        right: 5px;
        background-color: rgb(40, 0, 80);
        border-radius: 10px;
        width: 140px;
    }
    .option-list{
        list-style-type: none;
        padding:0;
        margin:0;
    }
    .option-list > li{
        border-top: 2px solid rgb(100, 0, 200);
        padding: 5px 0;
    }
    .option-list > li:hover{
        background-color: rgb(72, 0, 143);
        cursor: pointer;
    }
</style>