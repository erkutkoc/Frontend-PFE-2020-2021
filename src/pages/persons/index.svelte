<script>
  const fetchPersons = (async () => {
            const response = await fetch('//localhost:5000/api/persons');
            console.log(response);
        return await response.json()
        
        })()
</script>

<div style="text-align: center">
  <!-- {#each movies as [showId, title]}
    <h3>
      <a use:prefetch={options} href={$url('./:showId', { showId })}>
        {title}
      </a>
    </h3>
  {/each}
</div> -->
  {#await fetchPersons}

      <p>...waiting</p>
  {:then data}
      {#each data as person }
          <p>{person.name} - {person.number}</p>
      {/each }
  {:catch error}
      <p>An error shkuqskudqk!</p>
   {/await}
</div>