'''(java)
public class RestaurantFavorites { 
    public static void main(String[] args) {
        Restaurant favLunchPlace = new Restaurant();
        favLunchPlace.setName("Mcdonalds");
        favLunchPlace.setRating(0);
        favLunchPlace.print();
    }
}
'''

'''(java)
public class Restaurant { 
    public String name;
    public int rating;

    public void setName(String restaurantName) {
        name = restaurantName;
    }
    
    public void setRating(int restaurantRating) {
        rating = restaurantRating;
    }
    
    public void print() {
        System.out.println(name + " -- " + rating);
    }
}
'''
