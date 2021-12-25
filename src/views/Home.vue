<template>
<h1>Events for good</h1>
  <div class="events">
    <EventCard v-for="event in events" :key="event.id" :event="event"/>
  </div>
</template>

<script>
// @ is an alias to /src
import EventCard from "@/components/EventCard.vue"

export default {
  name: "Home",
  components: {
    EventCard,
  },
  data(){
    return {
      events: [
        {
          id: 2451985,
          category: 'animal welfare',
          title: 'Dog adoption day',
          description : 'Find your new canine friend at this event',
          location : 'Bark Island',
          date : '28 January 2022',
          time : '12:00',
          petsAllowed : true,
          organiser : 'Kaye Nine',
        },
         {
          id: 4582797,
          category: 'food',
          title: 'Community Gardening',
          description: 'Join us as we tend to the community edible plants.',
          location: 'Flora City',
          date: '14 March 2022',
          time: '10:00',
          petsAllowed: true,
          organiser: 'Fern Pollin'
        },
        {
          id: 8419988,
          category: 'sustainability',
          title: 'Beach Cleanup',
          description: 'Help pick up trash along the shore.',
          location: 'Playa Del Carmen',
          date: '22 July 2022',
          time: '11:00',
          petsAllowed: false,
          organiser: 'Carey Wales'
        }
      ]
    }
  }
}

/* a parent component (Home) creates child components (EventCard)
it holds data (events) to feed to child components having a 'prop' (:event) 

As we iterate over the events array to create a new EventCard for each event object, 
we pass that event object into a new :event prop that we added to the EventCard. 
Each EventCard then has all of the data it needs to display its own event info.
 */
</script>

<style scoped>
.events {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
