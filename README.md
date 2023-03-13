 <!-- СЮда скидаю костыли которые выкинул нахуй с проекта так как нашёл лучший вариант -->
 <!-- на случай если лучший вариаент полетит я верну костыль -->
 
 
 
 
 
 
 
 <!-- костыль на скролл хедера -->
 computed:{
        getScrollbarWidth() {
                // Creating invisible container
                const outer = document.createElement('div');
                outer.style.visibility = 'hidden';
                outer.style.overflow = 'scroll'; // forcing scrollbar to appear
                outer.style.msOverflowStyle = 'scrollbar'; // needed for WinJS apps
                document.body.appendChild(outer);

                // Creating inner element and placing it in the container
                const inner = document.createElement('div');
                outer.appendChild(inner);

                // Calculating difference between container's full width and the child width
                const scrollbarWidth = (outer.offsetWidth - inner.offsetWidth);

                // Removing temporary elements from the DOM
                outer.parentNode.removeChild(outer);

                return scrollbarWidth;

                },
            headerStyles(){
             return this.isMenuOpen ?{
                 paddingRight: `${this.getScrollbarWidth}px`,
                   
            }:{
                paddingRight: `${0}px`,
            }
        }   
    },