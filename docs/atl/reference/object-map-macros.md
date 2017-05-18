---
title: "Макросы схемы объекта | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 680087f4-9894-41dd-a79c-6f337e1f13c1
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: f03ca61c6ab3c550c316b380d34eb5fa4f3b61de
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="object-map-macros"></a>Макросы схемы объекта
Эти макросы определить сопоставления объектов и записей.  
  
|||  
|-|-|  
|[DECLARE_OBJECT_DESCRIPTION](#declare_object_description)|Позволяет указать объект класса текстовое описание вводится в карте объектов.|  
|[OBJECT_ENTRY_AUTO](#object_entry_auto)|Вводит объект ATL в схеме объекта, обновляет реестр и создает экземпляр объекта.|  
|[OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](#object_entry_non_createable_ex_auto)|Позволяет указать, что объект должен быть зарегистрирован и инициализирован, но не должен создаваться внешне через `CoCreateInstance`.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
   
##  <a name="declare_object_description"></a>DECLARE_OBJECT_DESCRIPTION  
 Можно указать описание для объекта класса.  
  
```
DECLARE_OBJECT_DESCRIPTION( x )
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 [in] Описание класса объекта.  
  
### <a name="remarks"></a>Примечания  
 ATL вводит это описание в карте объектов через [OBJECT_ENTRY](http://msdn.microsoft.com/en-us/abd10ee2-54f0-4f94-9ec2-ddf8f4c8c8cd) макрос.  
  
 `DECLARE_OBJECT_DESCRIPTION`реализует `GetObjectDescription` функции, который можно использовать для переопределения [CComCoClass::GetObjectDescription](ccomcoclass-class.md#getobjectdescription) метод.  

  
 `GetObjectDescription` Вызывается функция **IComponentRegistrar::GetComponents**. **IComponentRegistrar** интерфейс автоматизации позволяет регистрировать и отменять регистрацию отдельных компонентов в библиотеке DLL. При создании объекта регистрации компонента с помощью мастера проектов ATL, мастер автоматически будет реализовать **IComponentRegistrar** интерфейса. **IComponentRegistrar** обычно используется в Microsoft Transaction Server.  
  
 Дополнительные сведения о мастере проекта ATL см. в статье [создается проект ATL](../../atl/reference/creating-an-atl-project.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#123;](../../atl/codesnippet/cpp/object-map-macros_1.h)]  
  
##  <a name="object_entry_auto"></a>OBJECT_ENTRY_AUTO  
 Вводит объект ATL в схеме объекта, обновляет реестр и создает экземпляр объекта.  
  
```
OBJECT_ENTRY_AUTO( clsid, class )
```  
  
### <a name="parameters"></a>Параметры  
 `clsid`  
 [входные данные] Идентификатор CLSID объекта COM-класс, реализованного в классе C++ с именем `class`.  
  
 `class`  
 [входные данные] Имя класса C++, реализующего класс COM, представленный `clsid`.  
  
### <a name="remarks"></a>Примечания  
 Макросы записи объекта помещаются в глобальной области видимости в проекте для поддержки регистрации, инициализации и создания класса.  
  
 `OBJECT_ENTRY_AUTO`вводит указатели функций Создатель класса и класс создателя фабрики класса `CreateInstance` функции для данного объекта в карте автоматически создаваемых объектов ATL. Когда [CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver) является именем, он обновляет системного реестра для каждого объекта в схеме объекта.  

  
 В следующей таблице описывается способ получения информации, добавить к схеме объекта из класса, присвоенное данного макроса в качестве второго параметра.  
  
|Сведения о|Полученные из|  
|---------------------|-------------------|  
|Регистрация COM|[Макросы реестра](../../atl/reference/registry-macros.md)|  
|Создание фабрики классов|[Класс фабрики макросы](../../atl/reference/aggregation-and-class-factory-macros.md)|  
|Создание экземпляра|[Макросы агрегирования](../../atl/reference/aggregation-and-class-factory-macros.md)|  
|Категории регистрации компонентов|[Макросы категории](../../atl/reference/category-macros.md)|  
|Уровня класса инициализации и очистки|[ObjectMain](ccomobjectrootex-class.md#objectmain)|  

  
##  <a name="object_entry_non_createable_ex_auto"></a>OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO  
 Позволяет указать, что объект должен быть зарегистрирован и инициализирован, но не должен создаваться внешне через `CoCreateInstance`.  
  
```
OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO( clsid, class )
```  
  
### <a name="parameters"></a>Параметры  
 `clsid`  
 [входные данные] Идентификатор CLSID объекта COM-класс, реализованного в классе C++ с именем `class`.  
  
 `class`  
 [входные данные] Имя класса C++, реализующего класс COM, представленный `clsid`.  
  
### <a name="remarks"></a>Примечания  
 Макросы записи объекта помещаются в глобальной области видимости в проекте для поддержки регистрации, инициализации и создания класса.  
  
 `OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO`позволяет указать, что зарегистрирован объект и они будут инициализированы (см. [OBJECT_ENTRY_AUTO](#object_entry_auto) Дополнительные сведения), но не должны быть создаваемыми через `CoCreateInstance`.  
  
## <a name="see-also"></a>См. также  
 [Макросы](../../atl/reference/atl-macros.md)

