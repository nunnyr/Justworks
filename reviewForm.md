app.component('review-form', {
    template:
    /*html*/
    
    
    `<form class="review-form" @submit.prevent="onSubmit">
    <!--There will be 3 types of inputs in this form. 
        input (standard)
        textarea
        select
    -->
        <h3>Leave a review</h3>
        <label for="name">Name:</label>
        <input id="name" v-model="name">

        <label for="review">Review:</label>      
        <textarea id="review" v-model="review"></textarea>

        <label for="rating">Rating:</label>
        <!--We are using a modifier on the v-model to typecast the values
        as a number
        -->
        <select id="rating" v-model.number="rating">
        <option>5</option>
        <option>4</option>
        <option>3</option>
        <option>2</option>
        <option>1</option>
        </select>

        <input class="button" type="submit" value="Submit">
    </form>`,
    
    //storing data locally.
    //we are adding name, review, and rating bc those were the inputs
    //we had above
    data() {
        return {
            name: '',
            review: '',
            rating: null,
            
        }
    },
    methods: {
        //our onSubmit method goes in the methods
        onSubmit() {
            if(this.name === '' || this.review === '' || this.rating === null) {
                alert('Review is incomplete. Please fill out every field')
                return
            }

            let productReview = {
                name: this.name,
                review: this.review,
                rating: this.rating
            }
            //we have to send ^^ this information up.
            //bc we dont want the reviews to live on the form but on the product
            //the event listener below will create a productReview object containing
            //name, review, rating from our data
            
            //below will emit a 'review-submitted' event passing the productReview....defined
            //in the onSubmit() as the payload. 
            this.$emit('review-submitted', productReview)
    
            //we are clearing out the data fields
            this.name = ''
            this.review = ''
            this.rating = null
        }
    }
})

