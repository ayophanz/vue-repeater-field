# vue-repeater-field

# Image
<img src="repeater-img.JPG">

# Installation
download or clone this file into your components folder or any folder.

don't forget to specify the import path.

add this code to your app.js

      
    window.fire = new Vue();
    
   This line of code updates child when querying axios response
   
    self.$refs.childUpdate.fields = data here;
    
   This is requirements on updating child
   
    ref="childUpdate"


# Usage

    <template>
  
    <div class="form-group">
    
      <label for="feature">Features </label>

      <repeater-input :dataValue="featureData" ref="childUpdate" @dataFeature="featureData = $event"></repeater-input>

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
         
            },
            
            updateChildData() {
               let self = this;
               axios.get('/api/edit-room/'+id)
               .then(
               function (response) {
                  self.$refs.childUpdate.fields = JSON.parse(response.data.room_feature.value);
               });
            }
         
         }

    }

    </script>




# ENJOY
