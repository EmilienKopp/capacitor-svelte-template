<script lang="ts">
    import { Geolocation } from '@capacitor/geolocation';

    let loc: any;
    async function getCurrentPosition(){
        const res = await Geolocation.getCurrentPosition()
        loc = res;
    }
</script>

<div>
    <h1 class="text-red-300">Geolocation</h1>
    <p>Your location is:</p>
    <p>Latitude: {loc?.coords.latitude}</p>
    <p>Longitude: {loc?.coords.longitude}</p>

    <button on:click={getCurrentPosition}>
        Get Current Location
    </button>
</div>

<style>
    div {
        padding-top: 50px;
    }
</style>