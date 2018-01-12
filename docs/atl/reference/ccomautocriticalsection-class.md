---
title: "Класс CComAutoCriticalSection | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection::CComAutoCriticalSection
dev_langs: C++
helpviewer_keywords: CComAutoCriticalSection class
ms.assetid: 491a9d90-3398-4f90-88f5-fd2172a46b30
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d12abfceeebeb1cac89b510c14d7a9211173406e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ccomautocriticalsection-class"></a>Класс CComAutoCriticalSection
`CComAutoCriticalSection`Предоставляет методы для получения и освобождения владения объект критической секции.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CComAutoCriticalSection : public CComCriticalSection
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComAutoCriticalSection::CComAutoCriticalSection](#ccomautocriticalsection)|Конструктор.|  
|[CComAutoCriticalSection:: ~ CComAutoCriticalSection](#dtor)|Деструктор|  
  
## <a name="remarks"></a>Примечания  
 `CComAutoCriticalSection`похож на класс [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md), за исключением `CComAutoCriticalSection` автоматически инициализирует объект критической секции в конструкторе.  
  
 Как правило, используется `CComAutoCriticalSection` через `typedef` имя [AutoCriticalSection](ccommultithreadmodel-class.md#autocriticalsection). Это имя ссылается на `CComAutoCriticalSection` при [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) уже используется.  

  
 `Init` И `Term` методов из [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) недоступны при использовании этого класса.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)  
  
 `CComAutoCriticalSection`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcore.h  
  
##  <a name="ccomautocriticalsection"></a>CComAutoCriticalSection::CComAutoCriticalSection  
 Конструктор.  
  
```
CComAutoCriticalSection();
```  
  
### <a name="remarks"></a>Примечания  
 Вызывает функцию Win32 [InitializeCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms683472), который инициализирует объект критической секции.  
  
##  <a name="dtor"></a>CComAutoCriticalSection:: ~ CComAutoCriticalSection  
 Деструктор  
  
```
~CComAutoCriticalSection() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Деструктор вызывает [DeleteCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682552), который освобождает все системные ресурсы, используемые объектом критической секции.  
  
## <a name="see-also"></a>См. также  
 [Класс CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Класс CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)
