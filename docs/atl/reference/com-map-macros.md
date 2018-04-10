---
title: Макросы схемы COM | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- atlcom/ATL::BEGIN_COM_MAP
- atlcom/ATL::END_COM_MAP
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, COM map macros
ms.assetid: 0f33656d-321f-4996-90cc-9a7f21ab73c3
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e97db324dc8e130418419ef435e2665c84eb0b64
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="com-map-macros"></a>Макросы схемы COM
Эти макросы определяют схемы интерфейсов COM.  
  
|||  
|-|-|  
|[BEGIN_COM_MAP](#begin_com_map)|Отмечает начало карты записей COM интерфейс.|  
|[END_COM_MAP](#end_com_map)|Отмечает конец записях сопоставления COM. интерфейса.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
   
##  <a name="begin_com_map"></a>BEGIN_COM_MAP  
 Сопоставление COM — механизм, который предоставляет интерфейсы для объекта клиенту с помощью `QueryInterface`.  
  
```
BEGIN_COM_MAP(x)
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 [in] Имя класса объекта, который вы предоставляете интерфейсов.  
  
### <a name="remarks"></a>Примечания  
 [CComObjectRootEx::InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) возвращает только указателей для интерфейсов COM карты. Запуск схему интерфейсов с `BEGIN_COM_MAP` макрос, добавьте записи для каждого из интерфейсов с [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) макрос или одного из его вариантов и выполнить сопоставление с [END_COM_MAP](#end_com_map) макрос.  

  
### <a name="example"></a>Пример  
 От библиотеки ATL [BEEPER](../../visual-cpp-samples.md) образца:  
  
 [!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]  
  

  
##  <a name="end_com_map"></a>END_COM_MAP  
 Завершает определение сопоставление интерфейса COM.  
  
```
END_COM_MAP()
```  
  
## <a name="see-also"></a>См. также  
 [Макросы](../../atl/reference/atl-macros.md)   
 [Глобальные функции сопоставления COM](../../atl/reference/com-map-global-functions.md)
