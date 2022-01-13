<template>
  <div>
    {{ x }} {{ y }} {{ z }}
    <Scene>
      <SpotLight></SpotLight>

      <PointLight :position="[1.5, 0.5, 0]" specular="#FFFFFF"></PointLight>
      <Entity :position="[x, y, z]">
        <Box>
          <Material v-if="$store.state.color" :diffuse="$store.state.color">
            <Texture
              type="ambient"
              src="https://www.babylonjs-playground.com/textures/grass.png"
            ></Texture>
          </Material>
        </Box>
      </Entity>

      <!--  <Entity :position="[x, y, z]">
        <Animation property="position.x" :start="1" :end="10" :duration="15">
        </Animation>
        <Asset src="./airboat.obj">
          <Material :diffuse="$store.state.color">
            <Texture
              type="ambient"
              src="https://www.babylonjs-playground.com/textures/grass.png"
            ></Texture> </Material
        ></Asset>
      </Entity> -->
    </Scene>
  </div>
</template>

<script>
export default {
  data: () => ({ x: 0, y: 0, z: 5 }),
};
</script>

<style>
</style>