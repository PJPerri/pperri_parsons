<div id="distractorTest-sortableTrash" class="sortable-code"></div> 
<div id="distractorTest-sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="distractorTest-feedbackLink" value="Get Feedback" type="button" /> 
    <input id="distractorTest-newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "x = 1\n" +
    "while x &lt; 10:\n" +
    "	print(x+1)\n" +
    "    x += 1\n" +
    "x =+ 1 #distractor\n" +
    "x = 0 #distractor\n" +
    "while x &lt;=10: #distractor\n" +
    "while x &lt; 10 #distractor\n" +
    "while x &gt;10: #distractor";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "distractorTest-sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": true,
    "trashId": "distractorTest-sortableTrash"
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#distractorTest-newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#distractorTest-feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>
