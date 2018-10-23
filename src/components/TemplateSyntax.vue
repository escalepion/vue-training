<template>
  <div>
    <h1>Template Syntax</h1>

    <h3>Using raw html</h3>
    <p>Injecting string html via v-html: </p>
    <p>Using mustaches : {{ rawHtml }}</p>
    <p>Using v-html directive: <span v-html="rawHtml"></span></p>

    <h3>Using javascript expressions in mustache brackets: </h3>
    <p>Below will write 'Yes' if ok = true , else it should write 'No'</p>
    <p>{{ ok ? 'Yes' : 'No' }}</p>

    <h3>This will reverse the sentence : 'Hello world': </h3>
    {{ helloWorldMsg.split('').reverse().join('') }}
  </div>
</template>

<script>
export default {
  name: 'TemplateSyntax',

  data () {
    return {
      rawHtml: '<span style="color: blue">This shold be blue</span>',
      ok: true,
      helloWorldMsg: 'Hello World'
    }
  }
}
</script>

