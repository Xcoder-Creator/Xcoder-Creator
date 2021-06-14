<template>
  <div id="app">
    <h2 style="text-decoration: underline;">File/Document viewer in Vue</h2>
    <div class="pdf_display">
      <h3>For PDF:</h3>
      <pdf_viewer :file_content_pdf="file_value_pdf"></pdf_viewer>
    </div>

    <hr style="margin-top: 100px;">
    <div>
      <h3>For word:</h3>
      <word_viewer :file_content_word="file_value_word"></word_viewer>
    </div>

    <hr style="margin-top: 100px;">
    <div>
      <h3>For excel:</h3>
      <excel_viewer :file_content_excel="file_value_excel"></excel_viewer>
    </div>

    <hr style="margin-top: 100px;">
    <div>
      <h3>For presentation:</h3>
      <powerpoint_viewer :file_content_powerpoint="file_value_powerpoint"></powerpoint_viewer>
    </div>

    <hr style="margin-top: 100px;">
    <div>
      <h3>For video:</h3>
      <video_viewer :file_content_video="file_value_video"></video_viewer>
    </div>

    <hr style="margin-top: 100px;">
    <div>
      <h3>For text:</h3>
      <div><input type="file" name="inputfile" id="inputfile"></div>
      <pre id="output">

      </pre>
    </div>
  </div>
</template>

<script>
import pdf_viewer from './components/pdf_viewer.vue'
import word_viewer from './components/word_viewer.vue'
import excel_viewer from './components/excel_viewer.vue'
import powerpoint_viewer from './components/powerpoint_viewer.vue'
import video_viewer from './components/video_viewer.vue'

export default {
  name: 'App',

  components: { pdf_viewer, word_viewer, excel_viewer, powerpoint_viewer, video_viewer },

  data(){
    return {
      file_value_pdf: 'CSCU SLIDE INTRO.pdf',
      file_value_word: '',
      file_value_excel: '',
      file_value_powerpoint: '',
      file_value_video: 'Simple Video.mp4',
      file_value_text: '',
      text_output: ''
    }
  },

  methods: {
    
  },

  mounted(){
    document.getElementById('inputfile').addEventListener('change', function(){
      var fr = new FileReader();
      fr.onload = function(){
        document.getElementById('output').textContent = fr.result;
      }

      fr.readAsText(this.files[0]);
    })
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

#pdf_display_height {
  height: 100vh;
}

#file_value {
  padding: 6px;
}

#pdf_btn {
  padding: 6px;
}
</style>
