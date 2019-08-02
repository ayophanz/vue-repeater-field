# vue-repeater-field

# Installation
download or clone this file into your components folder or any folder.

don't forget to specify the import path.

# Usage
<code>
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

         }

    }

    </script>
</code>




# ENJOY
