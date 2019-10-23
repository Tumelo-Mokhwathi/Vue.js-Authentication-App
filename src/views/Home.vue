<template>
    <div class="container">
        <h3>Details</h3>
          <p class="text-right">Current Page: {{ currentPage }}</p>
          <b-table
            class="table table-striped"
            id="myDetails"
            :items="details"
            :per-page="perPage"
            :current-page="currentPage"
         ></b-table>
        <b-pagination
             v-model="currentPage"
             :total-rows="rows"
             :per-page="perPage"
              aria-controls="myDetails">
        </b-pagination>
    </div>
</template>

<script>
export default {
    computed:{
        rows(){
            return this.details.length
        }
    },
    data(){
        return {
            currentPage: 1,
            perPage: 5,
            details: [{
                IdNo: 1,
                FirstName: "Tumelo",
                LastName: "Mokhwathi",
                Age: 28,
                Address: "Tembisa"
            },
            {
                IdNo: 2,
                FirstName: "Maxwell",
                LastName: "Mokoena",
                Age: 32,
                Address: "Kempton Park"
            },
            {
                IdNo: 3,
                FirstName: "Tsietsi",
                LastName: "Thulari",
                Age: 35,
                Address: "Soweto"
            },
            {
                IdNo: 4,
                FirstName: "Maike",
                LastName: "Sibambo",
                Age: 30,
                Address: "Midrand"
            },
            {
                IdNo: 5,
                FirstName: "Thabo",
                LastName: "Tshabalala",
                Age: 23,
                Address: "Centurion"
            },
            {
                IdNo: 6,
                FirstName: "Maggie",
                LastName: "Kwena",
                Age: 25,
                Address: "Sunninghill"
            },
            {
                IdNo: 7,
                FirstName: "Dipuo",
                LastName: "Sibeko",
                Age: 37,
                Address: "Springs"
            },
            {
                IdNo: 8,
                FirstName: "Doctor",
                LastName: "khumalo",
                Age: 54,
                Address: "Germiston"
            }]
        }
    }
}
</script>