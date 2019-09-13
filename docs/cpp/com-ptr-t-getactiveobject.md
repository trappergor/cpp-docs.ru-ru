---
title: _com_ptr_t::GetActiveObject
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::GetActiveObject
helpviewer_keywords:
- GetActiveObject method [C++]
ms.assetid: 2fa94853-0410-4620-91f2-136dae923f9f
ms.openlocfilehash: f13a42878392f63096cdfcb405f3f91cc0efe451
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498897"
---
# <a name="_com_ptr_tgetactiveobject"></a>_com_ptr_t::GetActiveObject

**Блок, относящийся только к системам Microsoft**

Присоединяет к существующему экземпляру объекта, `CLSID` заданному `ProgID`или.

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

*рклсид*<br/>
`CLSID` Объект объекта.

*клсидстринг*<br/>
Строка в Юникоде, которая содержит `CLSID` значение (начиная с " **{** `ProgID`") или.

*клсидстринга*<br/>
Многобайтовая строка, использующая кодовую страницу ANSI, которая содержит `CLSID` значение (начиная с " **{** `ProgID`") или.

## <a name="remarks"></a>Примечания

Эти функции-члены вызывают **жетактивеобжект** , чтобы получить указатель на запущенный объект, зарегистрированный в OLE, а затем запрашивает тип интерфейса этого интеллектуального указателя. Результирующий указатель затем инкапсулируется в этот объект `_com_ptr_t`. `Release`метод вызывается для уменьшения числа ссылок для ранее инкапсулированного указателя. Эта подпрограммы возвращает значение HRESULT для обозначения успеха или неудачи.

- **Жетактивеобжект (** `rclsid` **)** подключается к существующему экземпляру объекта, `CLSID`заданному.

- **Жетактивеобжект (** `clsidString` **)** подключается к существующему экземпляру объекта при наличии строки в `CLSID` Юникоде, содержащей значение ( `ProgID`начиная с " **{** ") или.

- **Жетактивеобжект (** `clsidStringA` **)** подключается к существующему экземпляру объекта при наличии `CLSID` строки многобайтовых символов, содержащей значение ( `ProgID`начиная с " **{** ") или. Вызывает [MultiByteToWideChar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar), который предполагает, что строка находится в кодовой странице ANSI, а не на кодовой странице OEM.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _com_ptr_t](../cpp/com-ptr-t-class.md)