# vue-repeater-field

# Installation
download or clone this file into your components folder or any folder.

don't forget to specify the import path.

add this code to your app.js

      
    window.fire = new Vue();
   


# Usage

    <template>
  
    <div class="form-group">
    
      <label for="feature">Features </label>

      <repeater-input :dataValue="featureData" @dataFeature="featureData = $event"></repeater-input>

      <pre>{{ featureData }}</pre>
  
    </div> 

    </template>


    <script>
  
    import RepeaterInputComponent from '../../components/repeaterField';

    export default {

        components: {

         'repeater-field': RepeaterInputComponent

        },

         data() {

            return {

             featureData: [{}]

             }

         },
         
         methods: {
         
            reset() {
         
                fire.$emit('reset');
         
            }
         
         }

    }

    </script>




# ENJOY
