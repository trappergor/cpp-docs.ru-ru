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
ms.openlocfilehash: c295767070da04d0173e3299576338e700a1c6aa
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42597017"
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