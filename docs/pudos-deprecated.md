![](img/logo-spup.jpeg)



# API Integration Documentation

### February 2021

**INDEX Documentation Version Table	4**

- [**Endpoint –  How to get the list of PickUp Points**](#_toc_250049)

- [GET method](#_toc_250048)

- [Input](#_toc_250047)

- [Output table](#_toc_250046)

- [**Endpoint – How to get the list of PickUp Points**](#_toc_250045)

- [GET method](#_toc_250044)

- [Input](#_toc_250043)

- [Output table](#_toc_250042)

- [**Endpoint – Warehouse Keeper**](#_toc_250041)

- [Input and output table](#_toc_250040)

- [GET Method](#_toc_250039)

- [POST Method](#_toc_250038)

- [Input](#_toc_250037)

- [PATCH Method](#_toc_250036)

- [Input](#_toc_250035)

- [DELETE Method](#_toc_250034)

- [Input](#_toc_250033)

# <a name="_toc_250052"></a>General concepts

The following concepts will be used in the Smart Pickup business model:

**PUP:** Acronym for Smart Pickup.

**PUDO: “Pick Up - Drop Off”** Smart Pickup location. It refers to the premises that belong to the Smart Pickup network.

## <a name="_toc_250049"></a>Endpoint – Get List of PickUp Points

Obtaining the list of Smart Pickup pickup points is public. It can be accessed through the following URL:

### <a name="_toc_250048"></a>GET Method
<https://api.pickuppoint.cl/api/v1/public/pudos/> <https://api.pickuppoint.cl/api/v1/public/pudos/?category=tienda>


### <a name="_toc_250047"></a>Input

The endpoint for obtaining PUDOs (Associated Smart Pickup locations) can be filtered by commune, city, region, country or by other parameters delivered by the system such as access to parking or disabled access, and even by the name of the store. If the URL is consulted without filter parameters, all withdrawal points are obtained.

```json
{
  "results": [
    {
      "name": "Oficina Smart Pickup",
      "code": "SCL01",
      "is_inclusive": true,
      "is_parking": false,
      "location": {
        "latitude": "-33.4391627",
        "longitude": "-70.65540390000001"
      },
      "street": "Teatinos",
      "number": "380",
      "apartment": "",
      "commune": "Santiago",
      "city": "Santiago",
      "country": "Chile",
      "qualification": 1,
      "temporal_time_window": "Lun 08:00 - Vie 18:00",
      "category": "minimarket",
      "pudo_capacity": 90,
      "pudo_alert_capacity ": 13
    }
  ],
  "links": { "previous": null, "next": null }, "count": 1
}
```


It is also possible to use the following URL to obtain withdrawal points:

[https://api.pickuppoint.cl/api/v1/public/pudos/?\[campo\] iconstains=](https://api.pickuppoint.cl/api/v1/public/pudos/?%5Bcampo%5D__iconstains)

It is possible to filter the local Smart Pickups if they contain any letter or word within the filtered fields:

Example:

[https://api.pickuppoint.cl/api/v1/public/pudos/?city iconstains=S](https://api.pickuppoint.cl/api/v1/public/pudos/?city%20iconstains=S)


### <a name="_toc_250046"></a>Tabla de salida


| **Variable**  | **Type Value**       | **Required** |           **Example**           |                    **Description**                    |
| :------------ | :------------------- | :----------: | :-----------------------------: | :---------------------------------------------------: |
| Name          | String               |      -       |           La Pulperia           |                Smart Pickup Store name                |
| Code          | String               |      -       |              SCL01              |             Unique withdrawal point code              |
| Is\_inclusive | Boolean              |      -       |              True               | Informs if a pick-up point has disabled access or not |
| Is\_parking   | Boolean              |      -       |              False              |        Informs if a pick-up point has parking         |
| Location      | [latitude Longitude] |      -       | <p>[0,22546,</p><p>-2,1564]</p> | Inform latitude and longitude of the withdrawal point |
| Street        | String               |      -       |         Blanco encalada         |               Pick-up point street name               |
| Number        | String               |      -       |              245-A              |              Pick-up point street number              |
| Apartment     | String               |      -       |               25                |                   Apartment number                    |
| Commune       | String               |      -       |            Santiago             |     Commune where the withdrawal point is located     |


|          City           | String | -    |              Santiago              | City where the pick-up point is located                           |
| :---------------------: | :----: | :--- | :--------------------------------: | :---------------------------------------------------------------- |
|         Country         | String | -    |               Chile                | Country where the withdrawal point is located                     |
|      qualification      | Number | -    |                 5                  | Category to organize the withdrawal points                        |
| Temporal\_ti me\_window | String | -    | <p>Lun 08:00</p><p>– Vie 18:00</p> | Hours of operation of the withdrawal point                        |
|        Category         | String | -    |              oficina               | Withdrawal point category                                         |
|     Pudo\_capac ity     | Number | -    |                 50                 | Total number of packages the Withdrawal Point can manage          |
| Pudo\_alert\_ capacity  | Number | -    |                 12                 | Number that alerts of possible saturation of the withdrawal point |

# <a name="_toc_250045"></a>Endpoint – Get List of Withdrawal Points

Obtaining the list of Smart Pickup withdrawal points is public. It can be accessed through the following URL:

## <a name="_toc_250044"></a>GET Method
<https://api.pickuppoint.cl/api/v1/public/pudos/> <https://api.pickuppoint.cl/api/v1/public/pudos/?category=tienda>


### <a name="_toc_250043"></a>Input

The endpoint for obtaining PUDOs (Associated Smart Pickups) can be filtered by commune, city, region, country or by other parameters delivered by the system such as access to parking or disabled access, and even by the name of the withdrawal points. If the URL is consulted without filter parameters, all withdrawal points are obtained.

#### {
#### "results": [
#### {
#### "name": "Oficina Smart Pickup", "code": "SCL01",
#### "is\_inclusive": true, "is\_parking": false, "location": {
#### "latitude": "-33.4391627",
#### "longitude": "-70.65540390000001"
#### },
#### "street": "Teatinos", "number": "380",
#### "apartment": "", "commune": "Santiago", "city": "Santiago",
#### "country": "Chile", "qualification": 1,
#### "temporal\_time\_window": "Lun 08:00 - Vie 18:00", "category": "minimarket",
#### "pudo\_capacity": 90,
#### "pudo\_alert\_capacity ": 13


#### }
#### ],
#### "links": { "previous": null, "next": null }, "count": 1
#### }


It is also possible to use the following URL to obtain withdrawal points:

[https://api.pickuppoint.cl/api/v1/public/pudos/?\[campo\] iconstains=](https://api.pickuppoint.cl/api/v1/public/pudos/?%5Bcampo%5D__iconstains)

It is possible to filter the local Smart Pickups if they contain any letter or word within the filtered fields:

Example: [https://api.pickuppoint.cl/api/v1/public/pudos/?city iconstains=S](https://api.pickuppoint.cl/api/v1/public/pudos/?city__iconstains=S)


### <a name="_toc_250042"></a>Output table


| **Variable**  | **Output table**     | **Required** |           **Example**           |                    **Description**                    |
| :------------ | :------------------- | :----------: | :-----------------------------: | :---------------------------------------------------: |
| Name          | String               |      -       |           La Pulperia           |                Smart Pickup Store name                |
| Code          | String               |      -       |              SCL01              |             Unique withdrawal point code              |
| Is\_inclusive | Boolean              |      -       |              True               | Inform if a pick-up point has disabled access or not  |
| Is\_parking   | Boolean              |      -       |              False              |         Report if a pick-up point has parking         |
| Location      | [latitude Longitude] |      -       | <p>[0,22546,</p><p>-2,1564]</p> | Inform latitude and longitude of the withdrawal point |
| Street        | String               |      -       |         Blanco encalada         |               Pick-up point street name               |
| Number        | String               |      -       |              245-A              |              Pick-up point street number              |
| Apartment     | String               |      -       |               25                |                   Department number                   |
| Commune       | String               |      -       |            Santiago             |     Commune where the withdrawal point is located     |
| City          | String               |      -       |            Santiago             |        City where the pick-up point is located        |


|                         |        |      |                                    |                                                                                   |
| :---------------------- | :----- | :--- | :--------------------------------- | :-------------------------------------------------------------------------------- |
| Country                 | String | -    | Chile                              | Country where the withdrawal point is located                                     |
| qualification           | Number | -    | 5                                  | Category to organize the withdrawal points                                        |
| Temporal\_ti me\_window | String | -    | <p>Lun 08:00</p><p>– Vie 18:00</p> | Hours of operation of the withdrawal point                                        |
| Category                | String | -    | oficina                            | Withdrawal point category                                                         |
| Pudo\_capac ity         | Number | -    | 50                                 | Total number of packages the Withdrawal Point can manage                          |
| Pudo\_alert\_ capacity  | Number | -    | 12                                 | Number where an alert of possible saturation of the withdrawal point is triggered |

# <a name="_toc_250041"></a>Endpoint – Warehouse Keeper

Obtaining the list of wineries. It can be accessed through the following URL:

### <a name="_toc_250040"></a>Input and output table		


| **Variable** | **Value Type** | **Required** |    **Example**    |                **Description**                |
| :----------: | :------------- | :----------: | :---------------: | :-------------------------------------------: |
|     Name     | String         |     Yes      | API creation test |             Name of the warehouse             |
|     Code     | String         |     Yes      |        TTT        |             Unique warehouse code             |
|    Street    | String         |     Yes      |  Blanco encalada  |           Pick-up point street name           |
|    Number    | String         |     Yes      |        245        |           Pick-up point street name           |
|  Apartment   | String         |      No      |        25         |               Apartment number                |
|   Commune    | String         |     Yes      |     Santiago      | Commune where the withdrawal point is located |
|     City     | String         |     Yes      |  Metropolit ana   | Region where the withdrawal point is located  |
|   Country    | String         |     Yes      |       Chile       | Country where the withdrawal point is located |



## <a name="_toc_250039"></a>GET Method
[https://api.pickuppoint.cl/api/v1/commerce/warehouses/](https://api.pickuppoint.cl/api/v1/public/pudos/) [https://api.pickuppoint.cl/api/v1/commerce/warehouses/?page_size=10&page=1/](https://api.pickuppoint.cl/api/v1/public/pudos/)


#### {
#### "results": [
#### {
#### "code": "TTT",
#### "name": "Test de creación por API", "street": "Santo Domingo", "number": "1450",


#### "apartment": "1504", "commune": "Santiago",
#### "city": "Metropolitana de Santiago", "country": "chile",
#### "created": "2019-10-03T10:23:31.897770-03:00", "pk": 11
#### }
#### ],
#### "links": { "previous": null, "next": null }, "count": 1
#### }



## <a name="_toc_250038"></a>POST Method
[https://api.pickuppoint.cl/api/v1/commerce/warehouses/](https://api.pickuppoint.cl/api/v1/public/pudos/)

### <a name="_toc_250037"></a>Input

Code must be kept 3 characters; apartment can be sent as null.
#### {
#### "code": "TTT",
#### "name": "Test de creación por API", "street": "Santo Domingo", "number": "1450",
#### "apartment": "1504", "commune": "Santiago",
#### "city": "Metropolitana de Santiago", "country": "chile"
#### }

## <a name="_toc_250036"></a>PATCH method
[https://api.pickuppoint.cl/api/v1/commerce/warehouses/](https://api.pickuppoint.cl/api/v1/public/pudos/){{ pk of the warehouse to edit }}/

### <a name="_toc_250035"></a>Input

#### Send only what you want to edit
#### {
#### "name": "Nuevo Nombre"
#### }


## <a name="_toc_250034"></a>DELETE Method
[https://api.pickuppoint.cl/api/v1/commerce/warehouses/](https://api.pickuppoint.cl/api/v1/public/pudos/){{ pk of the warehouse to delete}}/

### <a name="_toc_250033"></a>Input

If this warehouse has already created orders, it is not possible to delete it to keep track.