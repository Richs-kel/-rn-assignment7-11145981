

## Description
This is a React Native mobile application for viewing and managing a list of products. Users can view available products, see detailed information about each product, and add or remove products from their cart. Data is fetched from an external API, and cart items are stored locally on the device.

## Design Choices
1. **Component-Based Architecture**: The app is divided into multiple components (`HomeScreen`, `ProductDetailScreen`, `CartScreen`) to ensure a modular and maintainable codebase.
2. **Drawer Navigation**: Implemented using `react-navigation` to provide easy navigation between screens.
3. **External API for Products**: Used `axios` to fetch product data asynchronously, ensuring up-to-date information.
4. **Local Storage**: Utilized `AsyncStorage` to store cart items locally, ensuring data persistence across app sessions.

## Data Storage Implementation
- **AsyncStorage**: Used to store selected items in the cart. When a user adds or removes items, the cart is updated in `AsyncStorage`, allowing for persistence.




## External API
- Products are fetched from [API URL]. Example request:
    ```javascript
    axios.get('https://api.example.com/products')
      .then(response => {
        setProducts(response.data);
      })
      .catch(error => {
        console.error(error);
      });
    ```

## Local Storage
- Example of adding an item to the cart and storing it in `AsyncStorage`:
    ```javascript
    const addToCart = async (product) => {
      try {
        let cart = await AsyncStorage.getItem('cart');
        cart = cart ? JSON.parse(cart) : [];
        cart.push(product);
        await AsyncStorage.setItem('cart', JSON.stringify(cart));
      } catch (error) {
        console.error(error);
      }
    };
    ```

![WhatsApp Image 2024-07-12 at 14 06 56_99c31b02](https://github.com/user-attachments/assets/dc1891a6-7230-41f8-9b2a-9f25a3b0a841)
![WhatsApp Image 2024-07-12 at 14 06 56_185d4f74](https://github.com/user-attachments/assets/a831df87-1999-4d3e-816c-a0d83f86416f)
![WhatsApp Image 2024-07-12 at 14 06 56_addca763](https://github.com/user-attachments/assets/98eb18e1-329b-438b-aeaa-d85a00c329ff)

