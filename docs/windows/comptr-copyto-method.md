---
title: Метод ComPtr::CopyTo | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::CopyTo
dev_langs:
- C++
helpviewer_keywords:
- CopyTo method
ms.assetid: 8801bc49-6db4-4393-a55f-a701ae3b8718
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5b387d52c9ab7b1d9033ce70d36e9f0aa5e5b33e
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642933"
---
# <a name="comptrcopyto-method"></a>Метод ComPtr::CopyTo
Копирует текущий или указанный интерфейс, связанный с этим **ComPtr** в заданный указатель.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CopyTo(  
   _Deref_out_ InterfaceType** ptr  
);  
  
HRESULT CopyTo(  
   REFIID riid,  
   _Deref_out_ void** ptr  
) const;  

template<typename U>  
HRESULT CopyTo(  
   _Deref_out_ U** ptr  
) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *U*  
 Имя типа.  
  
 *ptr*  
 После завершения операции представляет указатель на запрошенный интерфейс.  
  
 *riid*  
 Идентификатор интерфейса.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если выполнение прошло успешно; в противном случае — значение HRESULT, указывающее, почему неявный `QueryInterface` не удалось выполнить операцию.  
  
## <a name="remarks"></a>Примечания  
 Первая функция возвращает копию указателя на интерфейс, связанный с данным **ComPtr**. Эта функция всегда возвращает значение S_OK.  
  
 Вторая функция выполняет `QueryInterface` операции в интерфейсе, связанном с этим **ComPtr** для интерфейса, заданного параметром *riid* параметра.  
  
 Третья функция выполняет `QueryInterface` операции в интерфейсе, связанном с этим **ComPtr** для базового интерфейса параметра *U* параметра.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)