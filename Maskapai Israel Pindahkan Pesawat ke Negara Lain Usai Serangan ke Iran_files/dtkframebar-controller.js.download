$(function() {
    $('.dtkframebar__menu__kanal li').on('mouseover', function() {
        var $menuItem = $(this),
            $submenuWrapper = $('> .show-menu', $menuItem);

        // grab the menu item's position relative to its positioned parent
        var menuItemPos = $menuItem.position();
        var submenuHeight = $submenuWrapper.height();
        var frameHeight = $('.dtkframebar__menu__kanal').height() - submenuHeight;
        // place the submenu in the correct position relevant to the menu item
        if (menuItemPos.top > frameHeight) { //if looking for direct descendants then do .children('div').length
            $submenuWrapper.css({
                bottom: $('.dtkframebar__menu__kanal').height() - menuItemPos.top - 55,
                left: menuItemPos.left + Math.round($menuItem.outerWidth() * 0.98),
                top: 'inherit'
            });
            $submenuWrapper.addClass('edge');
        } else {
            $submenuWrapper.css({
                top: menuItemPos.top - 12,
                left: menuItemPos.left + Math.round($menuItem.outerWidth() * 0.98),
                bottom: 'inherit'
            });
            $submenuWrapper.removeClass('edge');
        }
    });
    // MENU
    $('.dtkframebar__menu__kanal ul li').each(function() {
        var $this = $(this);
        var framebarHeight = $('.dtkframebar__menu__kanal').height();
        if ($this.find('.show-menu li').length > 6 && $this.find('.show-menu li').length < 12) { //if looking for direct descendants then do .children('div').length
            $this.find('.show-menu').addClass('half');
        } else if ($this.find('.show-menu li').length > 12) {
            $this.find('.show-menu').addClass('three');
        }
    });
    $(window).click(function() {
        $('.dtkframebar__menu__kanal, .dtkframebar__menu__icon, .dtkframebar__user__notif__box, .dtkframebar__user__login__in__db').removeClass('show');
        changeMenuText();
    });
    $('.dtkframebar__menu__icon, .dtkframebar__menu__text').click(function(event) {
        $('.dtkframebar__menu__kanal, .dtkframebar__menu__icon').toggleClass('show');
        changeMenuText();
        event.preventDefault();
        event.stopPropagation();
    });
    function changeMenuText () {
        if ( $('.dtkframebar__menu__kanal').hasClass( "show" ) ) {
            $('.dtkframebar__menu__text').text("Tutup");
        } else if ( !$( this ).hasClass( "show" ) ) {
            $('.dtkframebar__menu__text').text("MENU");
        };
    }
    $('.dtkframebar__user__notif').click(function(event) {
        $('.dtkframebar__user__notif__box').toggleClass("show");
        event.stopPropagation();
    });
    $('.dtkframebar__user__login__in').click(function(event) {
        $('.dtkframebar__user__login__in__db').toggleClass("show");
        event.stopPropagation();
    });
    $('.dtkframebar__user__cookies .dtkframebar__btn').click(function() {
        $('.dtkframebar__user__cookies').hide();
    });

    // MODALBOX
    $(".box_modal_dtkid").click(function() {
        //alert();
        if ($('div').attr('id') == 'pop_box_now') {} else {
            $(this).removeAttr('href');
            var src = $(this).attr("alt");
            size = src.split('|');
            url = size[0],
                width = '100%',
                height = '100%'

            $("body").append("<div class='pop_box_dtkid scrollable' id='pop_box_now'><iframe frameborder='0' id='framebox' src=''></iframe></div>");
            $("#framebox").animate({
                height: height,
                width: width,
            }, 0, function(){
                event_listener();
            }).attr('src', url).css('position', 'absolute').css('top', '0').css('left', '0');
            $("body").css('overflow', 'hidden');
        }
    });

    function close_popup() {
        $("#pop_box_now").fadeOut(150);
        $("#pop_box_now").remove();
        $("body").css('overflow', 'scroll');
        clearInterval(n);
    }

    function event_listener() {
        n = setInterval(function() {
            if ("" !== window.location.hash) {
                if ("#close" == window.location.hash) close_popup();
                else if ("#undefined" == window.location.hash) close_popup();
                else {
                    if ("#main" == window.location.hash) return;
                }
                window.location.hash = "main"
            }
        }, 200)
    }

    function pop_next(src) {
        size = src.split('|');
        url = size[0],
            width = '100%',
            height = '100%'
        $("#framebox").animate({
            height: height,
            width: width,
        }, 0).attr('src', url).css('position', 'absolute').css('top', '0').css('left', '0');
    };

    function closepop() {
        $("#pop_box_now").remove();
        $("body").css('overflow', 'scroll');
    };
    $(".close_box").click(function (){
        closepop();
    });
    $(".close_box_in").click(function (){
        parent.closepop();
    });
});
