<template>
    <form @submit="onSubmit" class="add-form">
        <div class="form-control">
            <label>Uppgift</label>
            <input type="text" v-model="text" name="text" placeholder="Lägg till uppgift">
        </div>
        <div class="form-control">
            <label>Dag och Tid</label>
            <input type="text" v-model="day" name="day" placeholder="Lägg till dag och tid"
            >
        </div>
        <div class="form-control form-control-check">
            <label>Lägg till påminnelse</label>
            <input type="checkbox" v-model="reminder" name="reminder">
        </div>

        <input type="submit" value="Spara Uppgift" class="btn btn-block">
    </form>
</template>

<script>
export default {
  name: 'AddTask',
  data () {
    return {
      text: '',
      day: '',
      reminder: false
    }
  },
  methods: {
      onSubmit(e){
          e.preventDefault()
          
          if(!this.text){
              alert('Lägg till en uppgift')
              return
          }

          const newTask = {
              id: Math.floor(Math.random() * 100000),
              text: this.text,
              day: this.day
          }
      }
  }
}
</script>

<style scoped>
.add-form {
    margin-bottom: 40px;
}

.form-control {
    margin: 20px 0;
}

.form-control label {
    display: block;
}

.form-control input {
    width: 100%;
    height: 40px;
    margin: 5px;
    padding: 3px 7px;
    font-size: 17px;
}

.form-control-check {
    display: flex;
    align-items: center;
    justify-content: space-between;
}

.form-control-check label{
    flex: 1;
}

.form-control-check input{
    flex: 2;
    height: 20px;
}
</style>
