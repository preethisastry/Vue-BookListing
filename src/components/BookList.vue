<template>
    <div>
        <h1> {{ title }} </h1>
        <ul>
            <book-item v-for = "book in books" :book = "book"></book-item>
                       
        </ul>
        <hr>
        <book-form @addBook='appendBook'></book-form>
    </div>
</template>

<script>
    import BookItem from "./BookItem";
    import BookForm from "./BookForm";
    export default {
        name: 'BookList',
        data() {
            return {
                title:'Books To Read',
            
            books: [
                { title:'Self-Reliance', author: 'Ralph Waldo Emerson' },
                { title:'American Gods', author: 'Neil Gaiman' },
                { title:'Amusing Ourselves to Death', author: 'Neil Postman' },
                { title:'Harry Potter Series', author: 'JK Rowling' }

            ]
            };
         },
        components: {
            BookItem,
            BookForm
        },
        methods:{
            appendBook(bookTitle, bookAuthor){
                this.books.push({ title:bookTitle, author:bookAuthor });
            }
        }
    };
</script>

<style>
    h1, h2{
        font-weight: normal;
    }

    

    
</style>