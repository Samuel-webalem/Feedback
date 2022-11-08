<script>
  import Feedbackform from "./Feedbackform.svelte";
  import FeedbackList from "./FeedbackList.svelte";
  import Feedbackstats from "./Feedbackstats.svelte";

 let feedback = [
    {
      id: 1,
      rating: 10,
      text: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Aspernatur deleniti, quidem rerum minima ipsam commodi nesciunt perspiciatis illum temporibus autem? Iusto reprehenderit voluptate a odio eos officia totam eaque placeat.",
    },
    {
      id: 2,
      rating: 9,
      text: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Aspernatur deleniti, quidem rerum minima ipsam commodi nesciunt perspiciatis illum temporibus autem? Iusto reprehenderit voluptate a odio eos officia totam eaque placeat.",
    },
    {
      id: 3,
      rating: 8,
      text: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Aspernatur deleniti, quidem rerum minima ipsam commodi nesciunt perspiciatis illum temporibus autem? Iusto reprehenderit voluptate a odio eos officia totam eaque placeat.",
    },
  ];

  $: count = feedback.length;
  $: average = feedback.reduce((a, { rating }) => a + rating, 0)/feedback.length;
  const deletefeedback = (e) => {
    const itemid = e.detail;
    feedback = feedback.filter((item) => item.id != itemid);
  };
  const addfeedback = (e)=>{
      feedback=[e.detail,...feedback];
  }
</script>

<main class="container">
  <Feedbackform on:add-newfeedback={addfeedback}/>
  <Feedbackstats {average} {count}/>
  <FeedbackList feedback="{feedback}" on:delete-feedback="{deletefeedback}" />
</main>
