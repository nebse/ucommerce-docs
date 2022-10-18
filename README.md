# 9.6.3 Ucommerce documentation

Welcome to the Ucommerce documentation.

If you encounter any issues or feel that anything is missing, please contact us at [support@ucommerce.net](mailto:support@ucommerce.net)

## [System documentation](system-documentation)
Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Quisque porta augue sit amet felis semper pharetra. Nullam dictum odio sed sodales blandit. Curabitur commodo lorem diam, eu blandit metus pellentesque vitae. Sed nec eros eu sem aliquet maximus. Nam varius erat ante, vel elementum metus dapibus gravida. In aliquam, velit pharetra cursus aliquet, odio ipsum venenatis odio, sollicitudin consectetur est lectus sit amet massa. Suspendisse auctor eget felis a eleifend. In hac habitasse platea dictumst. Nunc nec ex neque. Nulla fermentum urna in nunc venenatis ultrices. Sed mattis ante eros, quis fringilla lorem condimentum at. Fusce tincidunt rutrum augue sed interdum. Integer eget pellentesque justo. Morbi erat turpis, sollicitudin facilisis commodo nec, bibendum sed nisi.

[Read more](system-documentation)

## [API reference](api-reference)
Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Quisque porta augue sit amet felis semper pharetra. Nullam dictum odio sed sodales blandit. Curabitur commodo lorem diam, eu blandit metus pellentesque vitae. Sed nec eros eu sem aliquet maximus. Nam varius erat ante, vel elementum metus dapibus gravida. In aliquam, velit pharetra cursus aliquet, odio ipsum venenatis odio, sollicitudin consectetur est lectus sit amet massa. Suspendisse auctor eget felis a eleifend. In hac habitasse platea dictumst. Nunc nec ex neque. Nulla fermentum urna in nunc venenatis ultrices. Sed mattis ante eros, quis fringilla lorem condimentum at. Fusce tincidunt rutrum augue sed interdum. Integer eget pellentesque justo. Morbi erat turpis, sollicitudin facilisis commodo nec, bibendum sed nisi.

[Read more](api-reference)

## [Release notes](release-notes)
Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Quisque porta augue sit amet felis semper pharetra. Nullam dictum odio sed sodales blandit. Curabitur commodo lorem diam, eu blandit metus pellentesque vitae. Sed nec eros eu sem aliquet maximus. Nam varius erat ante, vel elementum metus dapibus gravida. In aliquam, velit pharetra cursus aliquet, odio ipsum venenatis odio, sollicitudin consectetur est lectus sit amet massa. Suspendisse auctor eget felis a eleifend. In hac habitasse platea dictumst. Nunc nec ex neque. Nulla fermentum urna in nunc venenatis ultrices. Sed mattis ante eros, quis fringilla lorem condimentum at. Fusce tincidunt rutrum augue sed interdum. Integer eget pellentesque justo. Morbi erat turpis, sollicitudin facilisis commodo nec, bibendum sed nisi.

[Read more](release-notes)


## TEST PLAYGROUND
```csharp
[System.Web.Mvc.RoutePrefix("ucommerceapi/Basket")]
public class BasketController : ApiController
{
    [System.Web.Mvc.Route("Get")]
    public IHttpActionResult Get()
    {
        Ucommerce.Api.ITransactionLibrary transactionLibrary = ObjectFactory.Instance.Resolve<Ucommerce.Api.ITransactionLibrary>();
        if (!transactionLibrary.HasBasket())
        {
            return NotFound();
        }
 
        //Use Ucommerce's top level APIs to get current basket for the customer.
        Ucommerce.EntitiesV2.PurchaseOrder purchaseOrder = transactionLibrary.GetBasket(false);
 
        BasketModel basket = new BasketModel(purchaseOrder);
 
        return Ok(basket);
    }
}
```