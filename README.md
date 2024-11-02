# tests-test_models.py-showing-the-code-snippet-for-LIST-ALL-test-case-1pt-
import unittest
from myapp.models import Product

class TestProductModel(unittest.TestCase):

    def test_list_all_products(self):
        # Assuming you have a method in your Product model to list all products
        Product(name="Product 1", category="Category A", available=True).save()
        Product(name="Product 2", category="Category B", available=True).save()
        Product(name="Product 3", category="Category A", available=False).save()

        # Call the method to list all products
        all_products = Product.list_all()

        # Assert that the list contains all products
        self.assertEqual(len(all_products), 3)
        self.assertEqual(all_products[0].name, "Product 1")
        self.assertEqual(all_products[1].name, "Product 2")
        self.assertEqual(all_products[2].name, "Product 3")

if __name__ == '__main__':
    unittest.main()
