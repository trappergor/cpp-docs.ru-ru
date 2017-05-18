---
title: "Класс IAtlStringMgr | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IAtlStringMgr
- ATLSIMPSTR/ATL::IAtlStringMgr
- ATLSIMPSTR/ATL::Allocate
- ATLSIMPSTR/ATL::Clone
- ATLSIMPSTR/ATL::Free
- ATLSIMPSTR/ATL::GetNilString
- ATLSIMPSTR/ATL::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- shared classes, IAtlStringMgr
- memory, managing
- IAtlStringMgr class
ms.assetid: 722f0346-a770-4aa7-8f94-177be8dba823
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 4ff4aa01a6d30f377560962f98a5892bdcc37837
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="iatlstringmgr-class"></a>Класс IAtlStringMgr
Этот класс представляет интерфейс для `CStringT` диспетчера памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```
__interface IAtlStringMgr
```  
  
## <a name="members"></a>Члены  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[Выделить](#allocate)|Вызовите этот метод, чтобы выделить новую структуру строки данных.|  
|[Клон](#clone)|Этот метод возвращает указатель на новый диспетчер строку для использования с другим экземпляром `CSimpleStringT`.|  
|[Бесплатная](#free)|Этот метод используется для освобождения структуру строки данных.|  
|[GetNilString](#getnilstring)|Возвращает указатель на `CStringData` объект, используемый объектами, пустая строка.|  
|[Перераспределение](#reallocate)|Этот метод вызывается для перераспределения структуру строки данных.|  
  
## <a name="remarks"></a>Примечания  
 Этот интерфейс управляет памятью, используемые классами MFC независимые строки; Например, [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md), [CStringT](../../atl-mfc-shared/reference/cstringt-class.md), и [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md).  
  
 Этот класс также можно использовать для реализации диспетчера памяти для настраиваемой для класса пользовательской строки. Дополнительные сведения см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsimpstr.h  
  
##  <a name="allocate"></a>IAtlStringMgr::Allocate  
 Выделяет новую структуру строки данных.  
  
```
CStringData* Allocate(int nAllocLength,int nCharSize) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nAllocLength`  
 Число символов в новый блок памяти.  
  
 `nCharSize`  
 Размер (в байтах) тип знаков, используемых диспетчером строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на начало выделенного блока памяти.  
  
> [!NOTE]
>  Не указывают ошибки выделения путем создания исключения. Вместо этого ошибки выделения отслеживаемого, возвращая **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Вызов [IAtlStringMgr::Free](#free) или [IAtlStringMgr::ReAllocate](#reallocate) для освобождения памяти, выделенной с помощью данного метода.  
  
> [!NOTE]
>  Примеры использования см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="clone"></a>IAtlStringMgr::Clone  
 Возвращает указатель на новый диспетчер строку для использования с другим экземпляром `CSimpleStringT`.  
  
```
IAtlStringMgr* Clone() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает копию `IAtlStringMgr` объекта.  
  
### <a name="remarks"></a>Примечания  
 Обычно вызывается инфраструктурой при необходимости диспетчер строки для новой строки. В большинстве случаев **это** возвращается указатель.  
  
 Тем не менее если диспетчер памяти не поддерживает используется несколько экземпляров `CSimpleStringT`, указатель на диспетчер общий строки должны быть возвращены.  
  
> [!NOTE]
>  Примеры использования см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="free"></a>IAtlStringMgr::Free  
 Освобождает структуры данных строки.  
  
```
void Free(CStringData* pData) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pData`  
 Указатель на блок памяти, освобождаемой.  
  
### <a name="remarks"></a>Примечания  
 Освобождает указанный блок памяти ранее выделенный [выделение](#allocate) или [перераспределения](../../atl/reference/iatlmemmgr-class.md#reallocate).  
  
> [!NOTE]
>  Примеры использования см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="getnilstring"></a>IAtlStringMgr::GetNilString  
 Возвращает указатель на структуру строки данных для пустой строки.  
  
```
CStringData* GetNilString() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CStringData` объект, используемый для представления пустая строка.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для возврата представления является пустая строка.  
  
> [!NOTE]
>  При реализации диспетчера пользовательской строки, эта функция никогда не должны завершаются сбоем. Это можно обеспечить путем внедрения экземпляр **CNilStringData** в класс manager строку и возвращают указатель на этот экземпляр.  
  
> [!NOTE]
>  Примеры использования см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="reallocate"></a>IAtlStringMgr::Reallocate  
 Перераспределяет структуру строки данных.  
  
```
CStringData* Reallocate(  
 CStringData* pData,
 int nAllocLength,
 int nCharSize) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pData`  
 Указатель на память, выделенную ранее данным диспетчером памяти.  
  
 `nAllocLength`  
 Число символов в новый блок памяти.  
  
 `nCharSize`  
 Размер (в байтах) тип знаков, используемых диспетчером строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на начало выделенного блока памяти.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для изменения размера существующего блока памяти, заданные `pData`.  
  
 Вызов [IAtlStringMgr::Free](#free) для освобождения памяти, выделенной с помощью данного метода.  
  
> [!NOTE]
>  Примеры использования см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы общих библиотек ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)



