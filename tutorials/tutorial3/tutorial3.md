---
title: UnicTutorial5_09072018 1803 update
description: example
tags: [products>sap-hana, topic>api, tutorial>beginner]
primary_tag: tutorial:product/mobile
---
### Time to Complete
20 min


[ACCORDION-BEGIN [Step 1: ](Add custom code)]

1. Open the new `OrdersService.java` file and replace the template with the following code:

    ```cds
    namespace my.bookshop;
entity Books {
  key ID : UUID;
  title : String;
  genre : Genre;
  author : Association to Authors;
}
entity Authors {
  key ID : UUID;
  name : String;
  books : Association to many Books;
}
type Genre : enum {
  Mystery;
  Fiction;
  Drama;
}
service CatalogService {
  entity Books as projection on bookshop.Books;
  entity Authors as projection on bookshop.Authors;
}
    ```

1. Save your changes.

    >In this sample code, we set a value of 1000 for the property amount of each returned entity in reading operations.

[DONE]

[ACCORDION-END]

   
[ACCORDION-BEGIN [Step 2: ](Add custom code)]

1. Open the new `OrdersService.java` file and replace the template with the following code:

```java
    package my.bookshop;

    import java.util.ArrayList;
    import java.util.List;

    import com.sap.cloud.sdk.service.prov.api.*;
    import com.sap.cloud.sdk.service.prov.api.annotations.*;
    import com.sap.cloud.sdk.service.prov.api.exits.*;
    import com.sap.cloud.sdk.service.prov.api.request.*;
    import com.sap.cloud.sdk.service.prov.api.response.*;
    import org.slf4j.*;

    public class OrdersService {

      private static final Logger LOG = LoggerFactory.getLogger (OrdersService.class.getName());

      @BeforeRead (entity="Orders", serviceName="CatalogService")
      public BeforeReadResponse beforeReadOrders (ReadRequest req, ExtensionHelper h){
        LOG.error ("##### Orders - beforeReadOrders ########");
        return BeforeReadResponse.setSuccess().response();
      }

      @AfterRead (entity = "Orders", serviceName="CatalogService")
      public ReadResponse afterReadOrders (ReadRequest req, ReadResponseAccessor res, ExtensionHelper h) {
        EntityData ed = res.getEntityData();
        EntityData ex = EntityData.getBuilder(ed).addElement("amount", 1000).buildEntityData("Orders");
        return ReadResponse.setSuccess().setData(ex).response();
      }

      @AfterQuery (entity = "Orders", serviceName="CatalogService")
      public QueryResponse afterQueryOrders (QueryRequest req, QueryResponseAccessor res, ExtensionHelper h) {
        List<EntityData> dataList = res.getEntityDataList(); //original list
        List<EntityData> modifiedList = new ArrayList<EntityData>(dataList.size()); //modified list
        for(EntityData ed : dataList){
    		  EntityData ex = EntityData.getBuilder(ed).addElement("amount", 1000).buildEntityData("Orders");
    		  modifiedList.add(ex);
    	  }
        return QueryResponse.setSuccess().setData(modifiedList).response();
      }
    }  
```

1. Save your changes.

    >In this sample code, we set a value of 1000 for the property amount of each returned entity in reading operations.

[DONE]

[ACCORDION-END]
