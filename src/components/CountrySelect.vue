<template>
    <select @change="onChange()" 
        v-model="selected" class="block w-full p-3 mt-10 border rounded form-select ">
        <option value="0">Select Country</option>
        <option v-for="country in countries" :value="country.ID">
            {{country.Country}}
        </option>
    </select>
        
    
</template>

<script>
export default {
    name: 'CountrySelect',
    props: ['countries'],
    data(){
        return{
            selected: 0
        }
    }
}
</script>