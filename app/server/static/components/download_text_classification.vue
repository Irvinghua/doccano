<template lang="pug">
extends ./download.pug

block select-format-area
  label.radio
    input(
      type="radio"
      name="format"
      value="csv"
      v-bind:checked="format == 'csv'"
      v-model="format"
    )
    | CSV

  label.radio
    input(
      type="radio"
      name="format"
      value="json"
      v-bind:checked="format == 'json'"
      v-model="format"
    )
    | JSONL

  label.radio
    input(
      type="radio"
      name="format"
      value="txt"
      v-bind:checked="format == 'txt'"
      v-model="format"
    )
    | TEXT

block example-format-area
  pre.code-block(v-show="format == 'csv'")
    code.csv
      include ./examples/download_text_classification.csv
      | ...

  pre.code-block(v-show="format == 'json'")
    code.json
      include ./examples/download_text_classification.jsonl
      | ...

  pre.code-block(v-show="format == 'txt'")
    code.json
      include ./examples/download_text_classification.txt
      | ...
</template>

<script>
import uploadMixin from './uploadMixin';

export default uploadMixin;
</script>
