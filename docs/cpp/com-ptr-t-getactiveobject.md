---
title: _com_ptr_t::GetActiveObject | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::GetActiveObject
dev_langs:
- C++
helpviewer_keywords:
- GetActiveObject method [C++]
ms.assetid: 2fa94853-0410-4620-91f2-136dae923f9f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b9f77a894c39fc907367e5d4f8c7a687cc703331
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056512"
---
# <a name="comptrtgetactiveobject"></a>_com_ptr_t::GetActiveObject

**Блок, относящийся только к системам Microsoft**

Присоединяет к существующему экземпляру объекта, учитывая `CLSID` или `ProgID`.

## <a name="syntax"></a>Синтаксис

```
HRESULT GetActiveObject(
   const CLSID& rclsid
) throw( );
HRESULT GetActiveObject(
   LPCWSTR clsidString
) throw( );
HRESULT GetActiveObject(
   LPCSTR clsidStringA
) throw( );
```

#### <a name="parameters"></a>Параметры

*rclsid*<br/>
`CLSID` Объекта.

*clsidString*<br/>
Строка Юникода, которая содержит либо `CLSID` (начиная с "**{**«) или `ProgID`.

*clsidStringA*<br/>
Многобайтовая строка, с помощью кодовой страницы ANSI, которая содержит либо `CLSID` (начиная с "**{**«) или `ProgID`.

## <a name="remarks"></a>Примечания

Эти функции-члены вызывают **GetActiveObject** извлекаемого указатель на выполняющийся объект, который был зарегистрирован с OLE и затем запросы этого интеллектуального указателя интерфейса типа. Результирующий указатель затем инкапсулируется в этот объект `_com_ptr_t`. `Release` вызывается для уменьшения счетчика ссылок для ранее инкапсулированного указателя. Эта процедура возвращает значение HRESULT, указывающее успех или неудачу.

- **GetActiveObject (**`rclsid`**)** присоединяет к существующему экземпляру объекта, учитывая `CLSID`.

- **GetActiveObject (**`clsidString`**)** присоединяет к существующему экземпляру объекта, учитывая строку Юникода, которая содержит либо `CLSID` (начиная с "**{**«) или `ProgID`.

- **GetActiveObject (**`clsidStringA`**)** присоединяет к существующему экземпляру объекта, учитывая строку многобайтовых символов, которая содержит либо `CLSID` (начиная с "**{**«) или `ProgID`. Вызовы [MultiByteToWideChar](/windows/desktop/api/stringapiset/nf-stringapiset-multibytetowidechar), который предполагает, что строка имеет кодовую страницу ANSI, а не кодовую страницу OEM.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _com_ptr_t](../cpp/com-ptr-t-class.md)