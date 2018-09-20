---
title: Метод Module::GetClassObject | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GetClassObject
dev_langs:
- C++
helpviewer_keywords:
- GetClassObject method
ms.assetid: 95b0de1b-f728-4f96-9f44-f6ea71ce56e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 90a1b527d12e581c42fc9519e56d453f845e0b63
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419727"
---
# <a name="modulegetclassobject-method"></a>Метод Module::GetClassObject

Извлекает кэш фабрик классов.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetClassObject(
   REFCLSID clsid,
   REFIID riid,
   _Deref_out_ void **ppv,
   wchar_t* serverName = nullptr
);
```

### <a name="parameters"></a>Параметры

*CLSID*<br/>
Идентификатор класса.

*riid*<br/>
Запрошенный идентификатор интерфейса.

*ppv*<br/>
Указатель на возвращаемый объект.

*Имя_сервера*<br/>
Имя сервера, указанное в `ActivatableClassWithFactory`, `ActivatableClassWithFactoryEx`, или `ActivatableClass` макроса; или **nullptr** для получения имени сервера по умолчанию.

## <a name="return-value"></a>Возвращаемое значение

## <a name="remarks"></a>Примечания

Этот метод можно используйте только для модели COM, а не среду выполнения Windows. Этот метод предоставляет только `IClassFactory` методы.

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс Module](../windows/module-class.md)