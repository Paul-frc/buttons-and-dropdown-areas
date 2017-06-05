# buttons-and-dropdown-areas

WIP

```javascript

    (function(){
        var btn = document.querySelectorAll("[data-dropdown-trigger]");
        btn.forEach(function(ele){
            ele.addEventListener("click", function(){
                var dropDownAttrib = this.getAttribute("data-dropdown-trigger");
                var dropDownAreas;
                
                if(dropDownAttrib.indexOf(" ") !=-1) {
                    dropDownAreas = document.querySelectorAll("[data-dropdown-area*=" + dropDownAttrib + "]");
                }else {
                    var arrayOfTriggers = dropDownAreas.split(" ");
                    arrayOfTriggers.forEach(function(ele){
                        dropDownAreas = document.querySelectorAll("[data-dropdown-area*=" + dropDownAttrib + "]");
                    })
                }
                
                
                var otherTriggers = document.querySelectorAll("[data-dropdown-trigger=" + dropDownAttrib + "]");
                dropDownAreas.forEach(function(eles){
                    eles.classList.toggle("is-open");
                })
                otherTriggers.forEach(function(eles){
                    eles.classList.toggle("is-active");
                })
            })
        })
    })();

```
