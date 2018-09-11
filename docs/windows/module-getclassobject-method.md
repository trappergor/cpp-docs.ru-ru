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
ms.openlocfilehash: 3e0c8996823de35bbfd85d595556db933f34238a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599226"
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

*CLSID*  
Идентификатор класса.

*riid*  
Запрошенный идентификатор интерфейса.

*ppv*  
Указатель на возвращаемый объект.

*Имя_сервера*  
Имя сервера, указанное в `ActivatableClassWithFactory`, `ActivatableClassWithFactoryEx`, или `ActivatableClass` макроса; или **nullptr** для получения имени сервера по умолчанию.

## <a name="return-value"></a>Возвращаемое значение

## <a name="remarks"></a>Примечания

Этот метод можно используйте только для модели COM, а не среду выполнения Windows. Этот метод предоставляет только `IClassFactory` методы.

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также
[Класс Module](../windows/module-class.md)