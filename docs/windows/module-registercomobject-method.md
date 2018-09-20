---
title: Метод Module::RegisterCOMObject | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::RegisterCOMObject
dev_langs:
- C++
helpviewer_keywords:
- RegisterCOMObject method
ms.assetid: 59f223dc-03c6-429d-95da-b74b3f73b702
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7cccebf6e1c6004a2416f4fdeb254369f9aa7b72
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46410316"
---
# <a name="moduleregistercomobject-method"></a>Метод Module::RegisterCOMObject

Регистрирует один или несколько объектов модели COM, чтобы другие приложения могли к ним подключиться.

## <a name="syntax"></a>Синтаксис

```cpp
WRL_NOTHROW virtual HRESULT RegisterCOMObject(
   const wchar_t* serverName,
   IID* clsids,
   IClassFactory** factories,
   DWORD* cookies,
   unsigned int count);

```

### <a name="parameters"></a>Параметры

*Имя_сервера*<br/>
Полное имя сервера.

*идентификаторов CLSID*<br/>
Массив регистрируемых идентификаторов CLSID.

*фабрики*<br/>
Массив интерфейсов IUnknown объектов класса, чья доступность публикуется.

*Файлы cookie*<br/>
После завершения операции представляет массив указателей на значения, которые определяют зарегистрированные объекты класса. Эти значения в дальнейшем используются для отмены регистрации.

*count*<br/>
Количество идентификаторов CLSID, которые необходимо зарегистрировать.

## <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT (например, CO_E_OBJISREG), указывающее причину неудачного завершения операции.

## <a name="remarks"></a>Примечания

COM-объекты зарегистрированы с помощью перечислителя CLSCTX_LOCAL_SERVER перечисления CLSCTX.

Тип подключения к зарегистрированным объектам определяется сочетание текущего *comflag* параметр шаблона и перечислителя REGCLS_SUSPENDED перечисления.

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс Module](../windows/module-class.md)