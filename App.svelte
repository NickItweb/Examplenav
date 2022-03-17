<script>
import FeedbackList from '/public/components/FeedbackList.svelte'

  let feedback = [
    {
      id:1,
      rating:10,
      text:'Lorem ipsum, or lipsum as it is sometimes known, is dummy text used in laying out print, graphic or web designs. The passage is attributed to an unknown',
    },
    {
      id:2,
      rating:1,
      text:'Lorem ipsum, or lipsum as it is sometimes known, is dummy text used in laying out print, graphic or web designs. The passage is attributed to an unknown',
    },
    {
      id:3,
      rating:4,
      text:'Lorem ipsum, or lipsum as it is sometimes known, is dummy text used in laying out print, graphic or web designs. The passage is attributed to an unknown',
    }
  ]

  const deleteFeedback = (e) =>{
    const itemId = e.detail
    feedback = feedback.filter((item) => item.id != itemId)
  }
</script>

<style>
main{
   background:black;  
   
}
  .container {
   max-width:768px;
    margin:100px auto;
    padding:20px;
    
  }
 
</style>

<main class="container">
	<FeedbackList {feedback} on:delete-feedback = {deleteFeedback} />
	
</main>