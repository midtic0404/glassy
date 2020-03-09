<script>
    export let name;
    export let imageUrl;
</script>

<style>
    /* your styles go here */
    .card {
        width: 300px;
        text-align: center;
    }
    .column {
        display: flex;
        justify-content: center;
    }
</style>

<div class="column is-4">
    <div class="card">
    <div class="card-image">
        <figure class="image is-4by3">
        <img src="{imageUrl}" alt="Placeholder image">
        </figure>
    </div>
    <div class="card-content">
        <p class="subtitle">{name}</p>
    </div>
    </div>
</div>