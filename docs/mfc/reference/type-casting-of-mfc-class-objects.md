---
title: "Приведение объектов классов MFC типов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.classes
dev_langs:
- C++
helpviewer_keywords:
- macros [MFC], type casting
- pointers [MFC], type casting
- type casts [MFC]
- casting types [MFC]
- macros [MFC], casting pointers
ms.assetid: e138465e-c35f-4e84-b788-bd200ccf2f0e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1fc887ad855b00b525c74b66bfc70f2adb3312e3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="type-casting-of-mfc-class-objects"></a>Приведение типов объектов классов MFC
Макросы приведения типов предоставляют способ приведения заданный указатель на указатель, который указывает на объект определенного класса, с или без проверки, что допускается приведение.  
  
 В следующей таблице перечислены макросы приведения типов MFC.  
  
### <a name="macros-that-cast-pointers-to-mfc-class-objects"></a>Макросы, приведение указателей на объекты классов MFC  
  
|||  
|-|-|  
|[DYNAMIC_DOWNCAST](#dynamic_downcast)|Указатель на указатель на объект класса приводит при проверке того, если приведение является допустимым.|  
|[STATIC_DOWNCAST](#static_downcast)|Приводит указатель на объект из одного класса в указатель связанного типа. В отладочном построении вызывает **ASSERT** , если объект не является «вида» в целевой тип.|  
  
##  <a name="dynamic_downcast"></a>DYNAMIC_DOWNCAST  
 Предоставляет удобный способ приведение указателя на указатель на объект класса при проверке того, если приведение является допустимым.  
  
```   
DYNAMIC_DOWNCAST(class, pointer)  
```  
  
### <a name="parameters"></a>Параметры  
 `class`  
 Имя класса.  
  
 `pointer`  
 Указатель для приведения к указателю на объект типа `class`.  
  
### <a name="remarks"></a>Примечания  
 Преобразует макрос `pointer` параметр к указателю на объект `class` тип параметра.  
  
 Если объект, который ссылается указатель «вида» указанный класс макрос возвращает указатель на соответствующий. Если это не допустимые приведения, этот макрос возвращает **NULL**.  
  
##  <a name="static_downcast"></a>STATIC_DOWNCAST  
 Приведение *pobject* к указателю на *class_name* объекта.  
  
```   
STATIC_DOWNCAST(class_name, pobject)   
```  
  
### <a name="parameters"></a>Параметры  
 *class_name*  
 Имя класса, приведение.  
  
 *pObject*  
 Приведение к указателю на указатель *class_name* объекта.  
  
### <a name="remarks"></a>Примечания  
 *pObject* должно быть **NULL**, или указывает на объект класса, который является производным непосредственно или косвенно от *class_name*. В сборках приложения с **_DEBUG** препроцессора символ определен, макрос будет **ASSERT** Если *pobject* не **NULL**, или он указывает на объект, который не является «вида» указанный класс в *class_name* параметр (см. [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof)). В не - **_DEBUG** сборок, макрос выполняет приведение без проверки типа.  
  
 Класс, указанный в *class_name* параметр должен быть производным от `CObject` и необходимо использовать `DECLARE_DYNAMIC` и `IMPLEMENT_DYNAMIC`, `DECLARE_DYNCREATE` и `IMPLEMENT_DYNCREATE`, или `DECLARE_SERIAL` и `IMPLEMENT_SERIAL`макросов, как описано в статье [класс CObject: наследование класса от CObject](../../mfc/deriving-a-class-from-cobject.md).  
  
 Например, может привести указатель `CMyDoc`, который называется `pMyDoc`, указатель на **CDocument** с помощью следующего выражения:  
  
 [!code-cpp[NVC_MFCDocView#197](../../mfc/codesnippet/cpp/type-casting-of-mfc-class-objects_1.cpp)]  
  
 Если `pMyDoc` не указывает на объект, производный прямо или косвенно от **CDocument**, макрос будет **ASSERT**.  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
