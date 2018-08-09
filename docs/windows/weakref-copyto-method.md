---
title: Метод WeakRef::CopyTo | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::CopyTo
dev_langs:
- C++
helpviewer_keywords:
- CopyTo method
ms.assetid: f83de6da-b3d4-41a6-9845-cd725ecf3b75
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 90756dc8ff515a8c956778bf8c6392332a8f9ca9
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652751"
---
# <a name="weakrefcopyto-method"></a>Метод WeakRef::CopyTo
Присваивает указатель на интерфейс (при его наличии) указанной переменной указателя.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CopyTo(  
   REFIID riid,  
   _Deref_out_ IInspectable** ptr  
);  
  
template<typename U>  
HRESULT CopyTo(  
   _Deref_out_ U** ptr  
);  
  
HRESULT CopyTo(  
   _Deref_out_ IWeakReference** ptr  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *U*  
 Указатель `IInspectable` интерфейс. Если возникает ошибка *U* не является производным от `IInspectable`.  
  
 *riid*  
 Идентификатор интерфейса. Если возникает ошибка *riid* не является производным от `IWeakReference`.  
  
 *ptr*  
 Двойной косвенный указатель на `IInspectable` или `IWeakReference`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя. Дополнительные сведения см. в разделе **Замечания**.  
  
## <a name="remarks"></a>Примечания  
 Возвращаемое значение S_OK означает, что эта операция завершилась успешно, но не указывает, была ли слабая ссылка разрешена в строгую ссылку. Если возвращается значение S_OK, протестируйте этот параметр *p* строгую ссылку, то есть параметр *p* не соответствует **nullptr**.  
  
 Начиная с пакета SDK для Windows 10, этот метод устанавливает **WeakRef** экземпляр **nullptr** Если не удалось получить слабую ссылку, поэтому следует избегать произошла ошибка при проверке кода, проверяющего для WeakRef **nullptr**. Вместо этого проверьте *ptr* для **nullptr**.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс WeakRef](../windows/weakref-class.md)