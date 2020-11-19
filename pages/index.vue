<template>
 <Layout>
  <Header></Header>
  <Layout>
    <Content>
      <a-row>
      <a-col :span="24">
         <div style="height: 300px; width: 900px;">
          <SampleChart />
          </div>
      </a-col>
    </a-row>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
     <a-row>

      <a-col :span="24">
         <div style="height: 300px; width: 900px;">
          <chartjssample />
          </div>
      </a-col>
    </a-row>
    </Content>
  </Layout>
</Layout>
</template>

<script>
export default {}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
.marginrow{
  margin-bottom: 20px;
}

</style>

