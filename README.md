# Custom UI Tools
This repository includes some costumed or improved UI Components and Plugins which are not covered by standard frameworks , most of them based on Bootstrap 3/4 and PHP Laravel 5.5. Some of them are improved based on some previous authors, we will credit below, please contact us if you find missing someone. 
## Radio and Checkbox
Most of radios and checkboxs based on Bootstrap can't be customed easily, this type radio/checkbox can allow users click them just like normal buttons, developers can easily style them via change label's style.
<img src="/img/radio-and-checkbox.png" width="80%" height="80%">
### Checkbox
```
    <input type="checkbox" id="tag-1" name="tag_1" value="1" style="display:none;">
    <label class="check-label" for="tag-1">Tag Name 1</label>
```
### Radio
```
    <input type="radio" id="level-0" name="level" value="0" style="display:none;" checked>
    <label class="radio-label" for="level-0">None</label>
```
### Source Code
[Radio and Checkbox](/source/radio-and-checkbox.html)
## Phone Number Format
The US Phone number like (111)222-3333 is easier to reconginza. This JS / PHP Function can help developer quick format phone number.
<img src="/img/phone-format.png" width="80%" height="80%">
### JS Function
1. HTML Code
```
<label>Phone</label>
<input class="form-control phone" name="phone" type="text" required="true" />
```
2. JS Code
```
$(function () {
        PhoneInput();
    });

    function PhoneInput() {

        $('input[type=text].phone').on('keydown', function (e) {
            -1 !== $.inArray(e.keyCode, [46, 8, 9, 27, 13, 110, 189]) || (/65|67|86|88/.test(e.keyCode) && (e.ctrlKey ===
                    true || e.metaKey === true)) && (!0 === e.ctrlKey || !0 === e.metaKey) || 35 <= e.keyCode &&
                40 >= e.keyCode || (e.shiftKey || 48 > e.keyCode || 57 < e.keyCode) && (96 > e.keyCode || 105 <
                    e.keyCode) && e.preventDefault();

        });

        $('input[type=text].phone').on('keyup', function (e) {
            var ph = this.value.replace(/\D/g, '').substring(0, 10);
            // Backspace and Delete keys
            var deleteKey = (e.keyCode == 8 || e.keyCode == 46);
            var len = ph.length;
            if (len == 0) {
                ph = ph;
            } else if (len < 3) {
                ph = '(' + ph;
            } else if (len == 3) {
                ph = '(' + ph + (deleteKey ? '' : ') ');
            } else if (len < 6) {
                ph = '(' + ph.substring(0, 3) + ') ' + ph.substring(3, 6);
            } else if (len == 6) {
                ph = '(' + ph.substring(0, 3) + ') ' + ph.substring(3, 6) + (deleteKey ? '' : '-');
            } else {
                ph = '(' + ph.substring(0, 3) + ') ' + ph.substring(3, 6) + '-' + ph.substring(6, 10);
            }
            this.value = ph;
        });
    }
```
### PHP Function
```
class FormatPhoneNumber{
public function format($phoneNumber) {
    $phoneNumber = preg_replace('/[^0-9]/','',$phoneNumber);

    if(strlen($phoneNumber) > 10) {
        $countryCode = substr($phoneNumber, 0, strlen($phoneNumber)-10);
        $areaCode = substr($phoneNumber, -10, 3);
        $nextThree = substr($phoneNumber, -7, 3);
        $lastFour = substr($phoneNumber, -4, 4);

        $phoneNumber = '+'.$countryCode.' ('.$areaCode.') '.$nextThree.'-'.$lastFour;
    }
    else if(strlen($phoneNumber) == 10) {
        $areaCode = substr($phoneNumber, 0, 3);
        $nextThree = substr($phoneNumber, 3, 3);
        $lastFour = substr($phoneNumber, 6, 4);

        $phoneNumber = '('.$areaCode.') '.$nextThree.'-'.$lastFour;
    }
    else if(strlen($phoneNumber) == 7) {
        $nextThree = substr($phoneNumber, 0, 3);
        $lastFour = substr($phoneNumber, 3, 4);

        $phoneNumber = $nextThree.'-'.$lastFour;
    }

    return $phoneNumber;
    }
    
}
```
### Source Code
[Phone Format](/source/phone-format)
