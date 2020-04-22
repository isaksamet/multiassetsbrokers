---
permalink: "/contact/"
layout: default
---

<h1>Contact us</h1>

<div class="row py-4">
    <div class="col-md-12">
    <div class="well well-sm">
        <form class="form-horizontal" action="#" method="" id="contactform" >
        <fieldset>
        <!-- Name input-->
        <div class="form-group">
            <label class="col-md-3 control-label" for="name">Name</label>
            <div class="col-md-9">
            <input id="name" name="name" type="text" placeholder="Your name" class="form-control">
            </div>
        </div>
        <!-- Email input-->
        <div class="form-group">
            <label class="col-md-3 control-label" for="email">Your E-mail</label>
            <div class="col-md-9">
            <input id="email" name="email" type="text" placeholder="Your email" class="form-control">
            </div>
        </div>
        <!-- Message body -->
        <div class="form-group">
            <label class="col-md-3 control-label" for="message">Your message</label>
            <div class="col-md-9">
            <textarea class="form-control" id="message" name="message" placeholder="Please enter your message here..." rows="5"></textarea>
            </div>
        </div>
        <!-- Form actions -->
        <div class="form-group">
            <div class="col-md-12">
            <button type="submit" class="btn btn-primary">Submit</button>
            </div>
        </div>
        </fieldset>
        </form>
    </div>
    </div>
    <div id="thankyou" class="invisible">
        <h2>Thanks!! Your message was sent. We will contact you soon!</h2> 
    </div>
     <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
    <script type="text/javascript">
         $('#contactform').submit(function(event){
            event.preventDefault();
            $.post('https://hooks.zapier.com/hooks/catch/1463976/o5asj1q/', $(this).serialize(), function(response){
              if(response.result === 'error'){
                console.log(response.message);
                return;
              }
              // update view
              $('#contactform').addClass("invisible");
              $('#thankyou').toggleClass("invisible");           
            }, 'json');
          });
    </script>
</div>
