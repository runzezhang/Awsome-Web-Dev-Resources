# Custom UI Tools
This repository includes some costumed or improved UI Components and Plugins which are not covered by standard frameworks , most of them based on Bootstrap 3/4 and PHP Laravel 5.5. Some of them are improved based on some previous authors, we will credit below, please contact us if you find missing someone. 
## Radio and Checkbox
Most of radios and checkboxs based on Bootstrap can't be customed easily, this type radio/checkbox can allow users click them just like normal buttons, developers can easily style them via change label's style.
<<<<<<< HEAD
![radio and checkbox](/img/radio-and-checkbox.png)
### HTML Code
```
<!-- Checkbox -->
    <label>
        <input type="checkbox" id="tag-1" name="tag_1" value="1" style="display:none;">
        <label class="check-label" for="tag-1">Tag Name 1</label>
        <input type="checkbox" id="tag-2" name="tag_2" value="2" style="display:none;">
        <label class="check-label" for="tag-2">Tag Name 2</label>
        <input type="checkbox" id="tag-3" name="tag_3" value="3" style="display:none;">
        <label class="check-label" for="tag-3">Tag Name 3</label>
    </label>
    <!-- Radio -->
    <div>
        <div class="flex-div">
            <input type="radio" id="level-0" name="level" value="0" style="display:none;" checked>
            <label class="radio-label" for="level-0">None</label>
            <input type="radio" id="level-1" name="level" value="1" style="display:none;">
            <label class="radio-label" for="level-1">
                1
            </label>
            <input type="radio" id="level-2" name="level" value="2" style="display:none;">
            <label class="radio-label" for="level-2">
                2
            </label>
            <input type="radio" id="level-3" name="level" value="3" style="display:none;">
            <label class="radio-label" for="level-3">
                3
            </label>
        </div>
    </div>
```
### CSS Code
```
.check-label {
        margin: 10px;
        padding: 5px 10px;
        border-color: #ccc;
        border-style: solid;
        border-width: 2px;
        border-radius: 5px;
        color: #ccc;
        font-size: 16px;
        text-align: center;
        }
        input[type="checkbox"]:checked+label.check-label{
            border-color: #ce2828;
            color: #ce2828;
        }
        .radio-label {
            margin: 10px;
            padding: 5px 0px;
            border-color: #ccc;
            border-style: solid;
            border-width: 2px;
            border-radius: 5px;
            color: #ccc;
            font-size: 16px !important;
            width: 120px;
            text-align: center;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        input[type="checkbox"]:checked+label.radio-label{
            border-color: #ce2828;
            color: #ce2828;
        }
        input[type="radio"]:checked+label.radio-label{
            border-color: #ce2828;
            color: #ce2828;
        }
```
=======
<img src="/img/radio-and-checkbox.png" width="80%" height="80%">
>>>>>>> 28d4d3acfb5ca5a7a0830752e4ec256e499436c7
