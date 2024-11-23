<script>
    export let jsonData = [];
</script>

<table>
    <thead>
        <tr>
            {#if jsonData.length > 0}
                {#each Object.keys(jsonData[0]) as key}
                    <th>{key}</th>
                {/each}
            {/if}
        </tr>
    </thead>
    <tbody>
        {#each jsonData as row}
            <tr>
                {#each Object.values(row) as value}
                    <td>{value}</td>
                {/each}
            </tr>
        {/each}
    </tbody>
</table>

<style>
    table {
        width: 100%;
        border-collapse: collapse;
        margin: 20px 0;
    }
    th, td {
        border: 1px solid #ddd;
        padding: 8px;
        text-align: left;
    }
    th {
        background-color: #f4f4f4;
    }
</style>
