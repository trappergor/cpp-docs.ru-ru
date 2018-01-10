---
title: "Класс IAtlStringMgr | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- shared classes, IAtlStringMgr
- memory, managing
- IAtlStringMgr class
ms.assetid: 722f0346-a770-4aa7-8f94-177be8dba823
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 85b99b0b1f35ecbc35b4096ac8c2260d0a55680d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="iatlstringmgr-class"></a>Класс IAtlStringMgr
Этот класс представляет интерфейс для `CStringT` диспетчера памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```
__interface IAtlStringMgr
```  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[Выделить](#allocate)|Этот метод используется для выделения новой структуры данных строки.|  
|[Клон](#clone)|Вызовите этот метод для возврата указателя к новому менеджеру строку для использования с другим экземпляром `CSimpleStringT`.|  
|[Бесплатно](#free)|Этот метод для освобождения структуру данных строки.|  
|[GetNilString](#getnilstring)|Возвращает указатель на `CStringData` объект, используемый объектами, пустая строка.|  
|[Перераспределение](#reallocate)|Этот метод для перераспределения структуру данных строки.|  
  
## <a name="remarks"></a>Примечания  
 Этот интерфейс управляет памятью, используемые классами MFC независимых строка; Например, [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md), [CStringT](../../atl-mfc-shared/reference/cstringt-class.md), и [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md).  
  
 Этот класс также можно использовать для реализации диспетчера памяти для класса настраиваемой строки. Дополнительные сведения см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsimpstr.h  
  
##  <a name="allocate"></a>IAtlStringMgr::Allocate  
 Выделяет новую структуру данных строки.  
  
```
CStringData* Allocate(int nAllocLength,int nCharSize) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nAllocLength`  
 Число символов в новом блоке памяти.  
  
 `nCharSize`  
 Размер (в байтах) символьного типа, используемой диспетчером строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на начало выделенного блока памяти.  
  
> [!NOTE]
>  Не отправлять сигнал ошибки выделения путем создания исключения. Вместо этого получил сигнал ошибка выделения, возвращая **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Вызовите [IAtlStringMgr::Free](#free) или [IAtlStringMgr::ReAllocate](#reallocate) для освобождения памяти, выделенной с помощью данного метода.  
  
> [!NOTE]
>  Примеры использования см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="clone"></a>IAtlStringMgr::Clone  
 Возвращает указатель на новый диспетчер строку для использования с другим экземпляром `CSimpleStringT`.  
  
```
IAtlStringMgr* Clone() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает копию объекта `IAtlStringMgr` объекта.  
  
### <a name="remarks"></a>Примечания  
 Обычно вызывается платформой при необходимости диспетчер строки для новой строки. В большинстве случаев **это** возвращается указатель.  
  
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
 Освобождает блок памяти указанного, ранее выделенный методом [Allocate](#allocate) или [перераспределении](../../atl/reference/iatlmemmgr-class.md#reallocate).  
  
> [!NOTE]
>  Примеры использования см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="getnilstring"></a>IAtlStringMgr::GetNilString  
 Возвращает указатель на структуру данных строка для пустой строки.  
  
```
CStringData* GetNilString() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CStringData` объект, используемый для представления пустая строка.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для возврата представления является пустая строка.  
  
> [!NOTE]
>  При реализации диспетчера настраиваемой строки, эта функция никогда не должна закончиться откатом. Это можно проверить путем внедрения экземпляр **CNilStringData** в класс диспетчера строки и возвращают указатель на этот экземпляр.  
  
> [!NOTE]
>  Примеры использования см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="reallocate"></a>IAtlStringMgr::Reallocate  
 Перераспределение структуру данных строки.  
  
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
 Число символов в новом блоке памяти.  
  
 `nCharSize`  
 Размер (в байтах) символьного типа, используемой диспетчером строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на начало выделенного блока памяти.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для изменения размера существующего блока памяти, заданные `pData`.  
  
 Вызовите [IAtlStringMgr::Free](#free) для освобождения памяти, выделенной с помощью данного метода.  
  
> [!NOTE]
>  Примеры использования см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [ATL и MFC общие классы](../../atl-mfc-shared/atl-mfc-shared-classes.md)


