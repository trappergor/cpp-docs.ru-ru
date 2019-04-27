---
title: _com_ptr_t::GetActiveObject
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::GetActiveObject
helpviewer_keywords:
- GetActiveObject method [C++]
ms.assetid: 2fa94853-0410-4620-91f2-136dae923f9f
ms.openlocfilehash: 84e43de9c40baa3c596c68ed7739471c059cbac7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154855"
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