<template>
    <div>
        <DetailAuthors v-if="endpoint == 'authors'" />
        <DetailGenres v-else-if="endpoint == 'genres'" />
        <DetailPublishers v-else-if="endpoint == 'publishers'" />
        <DetailBooks v-else if="endpoint == 'books'" />
        <h1 v-else>
             Essa não :( <br/> {{endpoint || "Isso"}} não existir na API...
        </h1>
    </div>
</template>

<script>
import DetailAuthors from "../../views/authors/DetailAuthors";
import DetailGenres from "../../views/genres/DetailGenres";
import DetailBooks from "../../views/books/DetailBooks";
import DetailPublishers from "../../views/publishers/DetailPublishers";

export defaul {
    name: "DetailResourceBase",
    props: ["endpoint"],
    components:{
        DetailAuthors,
        DetailGenres,
        DetailPublishers,
        DetailBooks
    }
};
</script>

<style lang="scss" scoped></style>