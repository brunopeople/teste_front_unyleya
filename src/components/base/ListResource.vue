<template>
    <div>
      <ListAuthors
        v-if="endpoint == 'authors'"
        :onItemEvent="emitEventOpenModal"
      />
      <listGenres
        v-else-if="endpoint == 'genres'"
        :onItemEvent="emitEventOpenModal"
      />

      <ListBooks
        v-else-if="endpoint == 'books'"
        :onItemEvent="emitEventOpenModal"
      />

      <h1 v-else>
       Essa não :( <br/>
       {{endpoint || "Isso"}} não parece exitir...
      </h1>
    </div>
</template>


<script>
import ListAuthors from "../../views/authors/ListAuthors";
import listGenres from "../../views/genres/listGenres";
import ListPublishers from "../../views/publishers/ListPublishers";
import ListBooks from "../../views/books/ListBooks";

export default{
    name: "ListResourceBase",
    props: ["endpoint"],
    components:{
        ListAuthors,
        ListGenres,
        ListPublishers,
        ListBooks
    },

    methods:{
        emitEventOpenModal: function(id){
            this.$emit("open-detail, id);
        }
    }
};

</script>