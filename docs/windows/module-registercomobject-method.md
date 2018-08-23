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
ms.openlocfilehash: abbe93f5359171c88134ff61759e9edc63db2451
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610437"
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

*Имя_сервера*  
Полное имя сервера.

*идентификаторов CLSID*  
Массив регистрируемых идентификаторов CLSID.

*фабрики*  
Массив интерфейсов IUnknown объектов класса, чья доступность публикуется.

*Файлы cookie*  
После завершения операции представляет массив указателей на значения, которые определяют зарегистрированные объекты класса. Эти значения в дальнейшем используются для отмены регистрации.

*count*  
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