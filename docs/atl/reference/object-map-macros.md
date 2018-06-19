---
title: Макросы схемы объекта | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::DECLARE_OBJECT_DESCRIPTION
- atlcom/ATL::OBJECT_ENTRY_AUTO
- atlcom/ATL::OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO
dev_langs:
- C++
ms.assetid: 680087f4-9894-41dd-a79c-6f337e1f13c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 671fd80bc2c4ad320efb282fd659899756c2ecbc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362947"
---
# <a name="object-map-macros"></a>Макросы схемы объекта
Эти макросы определяют сопоставления объектов и записей.  
  
|||  
|-|-|  
|[DECLARE_OBJECT_DESCRIPTION](#declare_object_description)|Позволяет указать объект класса текстовое описание, которое будет введено в карте объектов.|  
|[OBJECT_ENTRY_AUTO](#object_entry_auto)|Вводит объекта ATL в карте объектов, обновляет реестр и создает экземпляр объекта.|  
|[OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](#object_entry_non_createable_ex_auto)|Позволяет указать, что объект должен быть зарегистрирован и инициализирован, но не должен создаваться внешне через `CoCreateInstance`.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
   
##  <a name="declare_object_description"></a>  DECLARE_OBJECT_DESCRIPTION  
 Позволяет указать текстовое описание для объекта класса.  
  
```
DECLARE_OBJECT_DESCRIPTION( x )
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 [in] Описание класса объекта.  
  
### <a name="remarks"></a>Примечания  
 ATL вводит это описание в карте объектов через [OBJECT_ENTRY](http://msdn.microsoft.com/en-us/abd10ee2-54f0-4f94-9ec2-ddf8f4c8c8cd) макрос.  
  
 `DECLARE_OBJECT_DESCRIPTION` реализует `GetObjectDescription` функции, которую можно использовать для переопределения [CComCoClass::GetObjectDescription](ccomcoclass-class.md#getobjectdescription) метод.  

  
 `GetObjectDescription` Функция вызывается функцией **IComponentRegistrar::GetComponents**. **IComponentRegistrar** — это интерфейс автоматизации, дает возможность регистрировать и отменять регистрацию отдельных компонентов в библиотеке DLL. При создании объекта регистрации компонента с помощью мастера проектов ATL, мастер автоматически будет реализовывать **IComponentRegistrar** интерфейса. **IComponentRegistrar** обычно используется в Microsoft Transaction Server.  
  
 Дополнительные сведения о мастере проекта ATL см. в статье [создается проект ATL](../../atl/reference/creating-an-atl-project.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#123](../../atl/codesnippet/cpp/object-map-macros_1.h)]  
  
##  <a name="object_entry_auto"></a>  OBJECT_ENTRY_AUTO  
 Вводит объекта ATL в карте объектов, обновляет реестр и создает экземпляр объекта.  
  
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
  
 `OBJECT_ENTRY_AUTO` вводит указатели функций класс создателя и класс создателя фабрики класса `CreateInstance` функции для этого объекта в карте объектов ATL автоматически созданный. Когда [CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver) является именем, он обновляет системного реестра для каждого объекта в карте объектов.  

  
 В следующей таблице описано, как получить информация, добавленная к схеме объекта из класса, заданную в качестве второго параметра к этому макросу.  
  
|Сведения о|Получено из|  
|---------------------|-------------------|  
|Регистрация для COM|[Макросы реестра](../../atl/reference/registry-macros.md)|  
|Создание фабрики классов|[Класс фабрики макросы](../../atl/reference/aggregation-and-class-factory-macros.md)|  
|Создание экземпляра|[Макросы агрегирования](../../atl/reference/aggregation-and-class-factory-macros.md)|  
|Компонент категории регистрации|[Макросы категорий](../../atl/reference/category-macros.md)|  
|Уровня класса инициализации и очистки|[ObjectMain](ccomobjectrootex-class.md#objectmain)|  

  
##  <a name="object_entry_non_createable_ex_auto"></a>  OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO  
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
  
 `OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO` позволяет указать, что объект должен зарегистрирован и инициализирован (см. [OBJECT_ENTRY_AUTO](#object_entry_auto) Дополнительные сведения), но не должен создаваться внешне через `CoCreateInstance`.  
  
## <a name="see-also"></a>См. также  
 [Макросы](../../atl/reference/atl-macros.md)
