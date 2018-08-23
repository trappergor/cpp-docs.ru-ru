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
ms.openlocfilehash: 791e9040d9e35c7dfb657cca38e26c01e86c86c4
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42594425"
---
# <a name="weakrefcopyto-method"></a>Метод WeakRef::CopyTo

Присваивает указатель на интерфейс (при его наличии) указанной переменной указателя.

## <a name="syntax"></a>Синтаксис

```cpp
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