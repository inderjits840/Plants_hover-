$(document).ready(function(){
    $('.planet').hover(
    function() {
      $('.planet').addClass('planet_hover');
      $(this).removeClass('planet_hover');
      $(this).addClass('planet_newclass');
      var data_company=$(this).attr('data-company');
      $('.content').css('z-index','0');
      $('.content').css('display','none');
      $('#'+data_company).css('display','block');
      $('#'+data_company).css('z-index','999');
      //console.log($(this).attr('idx'));
      $('#lCarousel').carousel(parseInt($(this).attr('idx')));
    },
    function() {
      $('.planet').removeClass('planet_hover');
      $('.planet').removeClass('planet_newclass');
      
      /*var data_company=$(this).attr('data-company');
      $('#'+data_company).css('display','none');*/
    }
  );  
  $('.close_btn').click(function() {
    $('.content').css('display','none');
    $('#lCarousel').carousel(0);
    });
    });
    
    function SelectionChanged()
    {
      var activeClass = $('#lCarousel .active').attr('sel');
      if(activeClass == "sun")
      {
        $('.planet').removeClass('planet_hover');
        $('.planet').removeClass('planet_newclass');
        $('.content').hide();
      }
      else
      {
        var selectedPlanet = $('#lSolarSystem > .'+activeClass+' > .planet');
        //alert('#lSolarSystem.'+activeClass+'.planet');
        //alert($(selectedPlanet).attr('class'));
        $('.planet').addClass('planet_hover');
        $(selectedPlanet).removeClass('planet_hover');
        $(selectedPlanet).addClass('planet_newclass');
        var data_company=$(selectedPlanet).attr('data-company');
        $('.content').css('z-index','0');
        $('.content').css('display','none');
        $('#'+data_company).css('display','block');
        $('#'+data_company).css('z-index','999');
      }
    }
