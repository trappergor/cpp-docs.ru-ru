---
title: "Класс CComObjectRoot | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComObjectRoot
- atlcom/ATL::CComObjectRoot
dev_langs: C++
helpviewer_keywords: CComObjectRoot class
ms.assetid: f8797c38-6e73-4f67-85c2-71654cffa8eb
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c2dc617eeb58594262ea272a0a4ef7da2865b73f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="ccomobjectroot-class"></a>Класс CComObjectRoot
Это определение типа для [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) шаблонизируется потоковая модель сервера по умолчанию.  
  
## <a name="syntax"></a>Синтаксис  
  
```
typedef CComObjectRootEx<CComObjectThreadModel> CComObjectRoot;
```  
  
## <a name="remarks"></a>Примечания  
 `CComObjectRoot`— `typedef` из [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) создания шаблона по умолчанию потоковая модель сервера. Таким образом [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) будет ссылаться либо [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) или [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md).  
  
 `CComObjectRootEx`обрабатывает объект управления счетчиками ссылок для неагрегированные и статистические объекты. Она содержит счетчик ссылок объекта, если объект не выполняется статистическая обработка и хранит указатель на внешняя Неизвестная строка, если объект выполняется статистическая обработка. Для статистических объектов `CComObjectRootEx` методы могут использоваться для обработки удалось создать внутренний объект, а для защиты внешний объект от удаления при выпуске внутреннего интерфейсов или внутренний объект удаляется.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
## <a name="see-also"></a>См. также  
 [Члены класса CComObjectRootEx](http://msdn.microsoft.com/en-us/e3ce9c3d-9c8e-4fe5-b682-8e56740a0164)   
 [CComObjectRootEx-класс](../../atl/reference/ccomobjectrootex-class.md)   
 [Класс CComAggObject](../../atl/reference/ccomaggobject-class.md)   
 [Класс CComObject](../../atl/reference/ccomobject-class.md)   
 [Класс CComPolyObject](../../atl/reference/ccompolyobject-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
