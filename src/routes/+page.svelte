
 <script>
import {Testimonials,Spotlight, Herotext,Button,Servicesgrid,Aboutgrid,Headers,Faq,Contact} from '$lib/index';
import Sexylogo from '../lib/assets/sexylogo.png'

//ABout section data

    const aboutsection = [
    [
      { title: "Box 1", description: "Description 1" },
      { title: "Box 2", description: "Description 2" }, 
      { title: "Box 2", description: "Description 2" }
    
    ]
  ];

//PUT THE IMAGES AND EDIT ACCORDINGLY
//PUT THE IMAGES IN src/lib/assets/testimonials/[name].svg

  const testimonials = [
  {
    quote:
      "We wish to thank Vikas Nath and his team at Magnimont for delivering our platform ahead of schedule. We transitioned smoothly thanks to the level of precision and the clean code. Could not recommend them more & I would 100% work with them again!",
    name: "Chelsey Childers",
    image: "/reviews/ChelseyChilders.webp", // You'll need to add actual image paths
  },
  {
    quote:
      "Choosing to partner with Magnimont for implementation of AI was indeed our smartest decision. They have a professional, responsive and technically brilliant team. They took it from our idea to reality without exceeding our budget.",
    name: "Kish Kuruppath",
    image: "/reviews/KishKuruppath.webp",
  },
  {
    quote:
      "Superb job of making web Divisions! Magnimont brought new life to our old site by creating a sharp design, fast-loading site that appeals to our customers. It is simply a testament to their experience in UI/UX.",
    name: "Varun Dosapati",
    image: "/reviews/VarunDosapati.webp",
  },
  {
    quote:
      "İ have no idea about this website but it's good to see what they discovered for the future and helping the nation with great skills good to be part of the team",
    name: "Bilal Bhat",
    image: "/reviews/BilalBhat.webp",
  },
];


//services section data

  const servicesgrid = [
  [
    { title: 'Code', description: 'Develop like a pro', icon: '<i class="fa-regular fa-lightbulb"></i>' },
    { title: 'Launch', description: 'Lift off to production', icon: '<i class="fa-regular fa-rocket"></i>' }
  ],
  [
    { title: 'Celebrate', description: 'Grab a beer!', icon: '<i class="fa-regular fa-champagne-glasses"></i>' },
    { title: 'Repeat', description: 'Do it all again', icon: '<i class="fa-regular fa-repeat"></i>' }
  ]
];

</script>

<!-- Hero section -->
 <div class='w-screen min-h-screen'>

     <Spotlight/>
     <div class="flex-usual-column herowrapper">
      <div class='herologo'>
        <img src={Sexylogo}>
      </div>  
      <div class='flex flex-col items-center'>

        <Herotext 
        title="Software for Ventures" 
        description="At Magnimont, we blend innovation with expertise to create tailored tech solutions that drive your business forward. From digital transformation to scalable growth, we're your partner in progress." 
        align='left'
        />
        <Button height="50px"/>
      </div> 
        </div>
        
    </div>


    <!-- About section -->
    <div class='w-screen min-h-screen flex-col flex justify-start items-center'>

         <Headers
         maxwidth='70vw'
         title='About Us'
         description='Magnimont is your strategic partner in digital transformation. We blend cutting-edge technology with creative innovation to build intelligent solutions that drive growth. From AI-powered chatbots and automation systems to compelling web experiences, we transform complex challenges into competitive advantages for forward-thinking businesses.'
         pt='0rem'
         align='center'
         />
         <Aboutgrid data={aboutsection}/>
        </div>


        <!-- Services section -->
        <div class='w-screen min-h-screen flex-col flex justify-start items-center'>


            <Headers
            maxwidth='70vw'
            title='Our Services'
            description=''
            pt='0rem'
            align='center'
            />
        <Servicesgrid data={servicesgrid}/>

        </div>

        <!-- Testimonials section -->


        <Headers
        maxwidth='100vw'
        title='Testimonials'
        description='what our clients say about us'
        pt='0rem'
        align='center'
        />

        <Testimonials
        items={testimonials}
        direction="left"
        speed="normal"
        pauseOnHover={true}
      />



      <!-- FAQ section -->


<div class='mb-[-8rem]'>
  <Headers
  maxwidth='100vw'
  title='FAQ'
  description=''
  pt='0rem'
  align='center'
  />
</div>
  

      <Faq
  title="Have Questions?"
  description="We’ve got answers to help you understand more about our services."
  faqs={[
    {
      question: 'What does Magnimont specialize in?',
      answer: 'We specialize in building innovative, scalable tech solutions tailored to your business needs.'
    },
    {
      question: 'How do I get started?',
      answer: 'Just reach out to us via our contact page or email, and we’ll set up a consultation to understand your goals.'
    },
    {
      question: 'Can you handle large-scale systems?',
      answer: 'Absolutely. Our team is experienced with enterprise-grade architecture and deployment.'
    }
  ]}
/>

<!-- I am NOT DOING CONTACT PAGE FUCK FORM HANDLING THAT IS SO ASS 
              jokes aside pls do the form section here
              or if you cant then ill do it anyways but i would like to avoid it if possible
              specially since i dont know much backend 
-->

<!-- nevermind -->

<!-- contact page -->

<Headers
maxwidth='100vw'
title='Contact us'
description='get in touch with ease'
pt='0rem'
align='center'
/>


<Contact
  title="Let's Talk" 
  description="Have a project or idea? Send us a message and we’ll get back to you soon." 
/>
