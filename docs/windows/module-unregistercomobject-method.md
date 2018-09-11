---
title: Метод Module::UnregisterCOMObject | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::UnregisterCOMObject
dev_langs:
- C++
helpviewer_keywords:
- UnregisterCOMObject method
ms.assetid: 5d377525-0385-482a-a215-6e8a1f032861
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3409e0e2c1cac5f3934902523edd2653839989ed
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42575762"
---
# <a name="moduleunregistercomobject-method"></a>Метод Module::UnregisterCOMObject

Отменяет регистрацию одного или нескольких объектов модели COM, что предотвращает подключение к ним других приложений.

## <a name="syntax"></a>Синтаксис

```cpp
virtual HRESULT UnregisterCOMObject(
   const wchar_t* serverName,
   DWORD* cookies,
   unsigned int count
```

### <a name="parameters"></a>Параметры

*Имя_сервера*  
(Не используется)

*Файлы cookie*  
Массив указателей на значения, которые идентифицируют объекты класса для отмены регистрации. Массив был создан с [RegisterCOMObject](../windows/module-registercomobject-method.md) метод.

*count*  
Количество классов для отмены регистрации.

## <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее причину неудачного завершения операции.

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также
[Класс Module](../windows/module-class.md)