
$(".pie-chart").each(function() {
  var $pieChart = $(this);
  
  var percent = $pieChart.attr('data-percent');
  var $path = $pieChart.find('path');
  var pathLength = $path[0].getTotalLength();
  var offsetTo = pathLength * (percent / 100);

  $pieChart.attr('data-percent', 0);
  $path[0].style.strokeDashoffset = 0;

  $pieChart.one("inview", function(event) {
    $path.animate(
      {'strokeDashoffset': offsetTo}, 
      { duration: 2500,
        step: function (now) {
          $pieChart.attr('data-percent', Math.round(now/pathLength*100));
        }
      });
  });
});