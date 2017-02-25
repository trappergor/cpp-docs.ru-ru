---
title: "CComObjectRoot Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComObjectRoot"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComObjectRoot class"
ms.assetid: f8797c38-6e73-4f67-85c2-71654cffa8eb
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CComObjectRoot Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Это typedef [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) templatized по умолчанию потоковой модели сервера.  
  
## Синтаксис  
  
```  
  
typedef CComObjectRootEx<CComObjectThreadModel> CComObjectRoot;  
  
```  
  
## Заметки  
 `CComObjectRoot` `typedef` [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) templatized по умолчанию потоковой модели сервера.  Таким образом будет ссылаться на [CComObjectThreadModel](../Topic/CComObjectThreadModel.md) или [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) или [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md).  
  
 Элемент управления обрабатывает `CComObjectRootEx` count ссылки на объект и для nonaggregated и агрегированных объектов.  Он содержит счетчик ссылок на объект если объект не статистической обработки, и сохраняет указатель на внешний неизвестный, если объект статистической обработки.  Для агрегированных объектов, методы `CComObjectRootEx` могут быть использованы для обработки ошибка внутреннего объекта для проектирования и защитить внешний объект из удаления, если внутренние интерфейсы освобождены или внутренний объект удаляется.  
  
## Требования  
 **Header:**  atlcom.h  
  
## См. также  
 [CComObjectRootEx Class Members](http://msdn.microsoft.com/ru-ru/e3ce9c3d-9c8e-4fe5-b682-8e56740a0164)   
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)   
 [CComAggObject Class](../../atl/reference/ccomaggobject-class.md)   
 [CComObject Class](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject Class](../../atl/reference/ccompolyobject-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)