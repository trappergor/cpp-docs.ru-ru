---
title: "Приведение объектов классов MFC введите | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.classes
dev_langs:
- C++
helpviewer_keywords:
- macros, type casting
- pointers, type casting
- type casts
- casting types
- macros, casting pointers
ms.assetid: e138465e-c35f-4e84-b788-bd200ccf2f0e
caps.latest.revision: 15
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: f1ae094e7085017f03daab3f73323da13ab1be39
ms.lasthandoff: 02/24/2017

---
# <a name="type-casting-of-mfc-class-objects"></a>Приведение типов объектов классов MFC
Макросы приведения типов предоставляют способ приведения заданный указатель на указатель, указывающий на объект определенного класса, с или без проверки, что допускается приведение.  
  
 В следующей таблице перечислены макросы приведения типов MFC.  
  
### <a name="macros-that-cast-pointers-to-mfc-class-objects"></a>Макросы, приведение указателей на объекты классов MFC  
  
|||  
|-|-|  
|[DYNAMIC_DOWNCAST](#dynamic_downcast)|При проверке, если допускается приведение приводит указатель на указатель на объект класса.|  
|[STATIC_DOWNCAST](#static_downcast)|Приводит указатель на объект из одного класса в указатель связанного типа. В отладочном построении вызывает **ASSERT** , если объект не является «вида» тип целевого объекта.|  
  
##  <a name="a-namedynamicdowncasta--dynamicdowncast"></a><a name="dynamic_downcast"></a>DYNAMIC_DOWNCAST  
 Предоставляет удобный способ приведение указателя на указатель на объект класса при проверке, если приведение является допустимым.  
  
```   
DYNAMIC_DOWNCAST(class, pointer)  
```  
  
### <a name="parameters"></a>Параметры  
 `class`  
 Имя класса.  
  
 `pointer`  
 Указатель для приведения к указателю на объект типа `class`.  
  
### <a name="remarks"></a>Примечания  
 Макрос будет привести `pointer` параметр в указатель на объект `class` тип параметра.  
  
 Если объект, который ссылается указатель «вида» идентифицируемый класс макрос возвращает указатель на соответствующий. Если это не юридические приведения, этот макрос возвращает **NULL**.  
  
##  <a name="a-namestaticdowncasta--staticdowncast"></a><a name="static_downcast"></a>STATIC_DOWNCAST  
 Приведение *pobject* указатель на *class_name* объекта.  
  
```   
STATIC_DOWNCAST(class_name, pobject)   
```  
  
### <a name="parameters"></a>Параметры  
 *class_name*  
 Имя класса, приведение.  
  
 *pObject*  
 Приведение к указателю на указатель *class_name* объекта.  
  
### <a name="remarks"></a>Примечания  
 *pObject* должно быть **NULL**, или указывает на объект класса, который является производным непосредственно или косвенно от *class_name*. В сборках приложения с помощью **_DEBUG** определен символ препроцессора, макрос будет **ASSERT** Если *pobject* не **NULL**, или он указывает на объект, который не является «вида» класс, указанный в *class_name* параметр (см. [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof)). В не **_DEBUG** сборок, макрос выполняет приведение без проверки типа.  
  
 Класс, указанный в *class_name* параметр должен быть производным от `CObject` и необходимо использовать `DECLARE_DYNAMIC` и `IMPLEMENT_DYNAMIC`, `DECLARE_DYNCREATE` и `IMPLEMENT_DYNCREATE`, или `DECLARE_SERIAL` и `IMPLEMENT_SERIAL` макросов, как описано в статье [класс CObject: наследование класса от CObject](../../mfc/deriving-a-class-from-cobject.md).  
  
 Например, может привести указатель `CMyDoc`, который называется `pMyDoc`, указатель на **CDocument** с помощью следующего выражения:  
  
 [!code-cpp[NVC_MFCDocView&#197;](../../mfc/codesnippet/cpp/type-casting-of-mfc-class-objects_1.cpp)]  
  
 Если `pMyDoc` не указывает на объект, производный прямо или косвенно от **CDocument**, макрос будет **ASSERT**.  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)

