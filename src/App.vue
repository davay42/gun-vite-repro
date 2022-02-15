<script setup>
import Gun from "gun/gun";
import "gun/lib/then";
import "gun/lib/radix";
import "gun/lib/radisk";
import "gun/lib/store";
import "gun/lib/rindexed";
// import "gun/lib/webrtc";
import "gun/nts";


const gun = Gun();

const db = gun.get('test')

db.map().on((d, k) => {
  console.log(k, d)
})

function add() {
  db.get(Date.now()).put(Math.random())
}

</script>

<template>
  <main>
    <button @click="add()">ADD</button>
  </main>
</template>

