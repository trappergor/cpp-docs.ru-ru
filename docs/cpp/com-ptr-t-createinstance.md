---
title: _com_ptr_t::CreateInstance
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::CreateInstance
helpviewer_keywords:
- CreateInstance method [C++]
ms.assetid: ab89b0e1-9da3-4784-a079-58b17340f111
ms.openlocfilehash: 82b180b3f40683495ed2cfa284bdae8e1afaef9e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498654"
---
# <a name="_com_ptr_tcreateinstance"></a>_com_ptr_t::CreateInstance

**Блок, относящийся только к системам Microsoft**

Создает новый экземпляр объекта с `CLSID` заданным или. `ProgID`

## <a name="syntax"></a>Синтаксис

```
HRESULT CreateInstance(
   const CLSID& rclsid,
   IUnknown* pOuter=NULL,
   DWORD dwClsContext = CLSCTX_ALL
) throw( );
HRESULT CreateInstance(
   LPCWSTR clsidString,
   IUnknown* pOuter=NULL,
   DWORD dwClsContext = CLSCTX_ALL
) throw( );
HRESULT CreateInstance(
   LPCSTR clsidStringA,
   IUnknown* pOuter=NULL,
   DWORD dwClsContext = CLSCTX_ALL
) throw( );
```

#### <a name="parameters"></a>Параметры

*рклсид*<br/>
`CLSID` Объект объекта.

*клсидстринг*<br/>
Строка в Юникоде, которая содержит `CLSID` значение (начиная с " **{** `ProgID`") или.

*клсидстринга*<br/>
Многобайтовая строка, использующая кодовую страницу ANSI, которая содержит `CLSID` значение (начиная с " **{** `ProgID`") или.

*двклсконтекст*<br/>
Контекст для выполняющегося исполняемого кода.

*паутер*<br/>
Внешняя неизвестная для [агрегирования](../atl/aggregation.md).

## <a name="remarks"></a>Примечания

Эти функции-члены вызывают `CoCreateInstance` для создания нового COM-объект, а затем запрашивают тип интерфейса данного интеллектуального указателя. Результирующий указатель затем инкапсулируется в этот объект `_com_ptr_t`. `Release`метод вызывается для уменьшения числа ссылок для ранее инкапсулированного указателя. Эта подпрограммы возвращает значение HRESULT для обозначения успеха или неудачи.

- **CreateInstance (** *рклсид* **,** *двклсконтекст* **)** Создает новый выполняющийся экземпляр объекта, `CLSID`используя объект.

- **CreateInstance (** *клсидстринг* **,** *двклсконтекст* **)** Создает новый запущенный экземпляр объекта с заданной строкой Юникода, содержащей `CLSID` значение (начиная с " **{** `ProgID`") или.

- **CreateInstance (** *клсидстринга* **,** *двклсконтекст* **)** Создает новый запущенный экземпляр объекта с заданной строкой многобайтовых символов, содержащей `CLSID` либо (начиная с " **{** `ProgID`"), либо. Вызывает [MultiByteToWideChar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar), который предполагает, что строка находится в кодовой странице ANSI, а не на кодовой странице OEM.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _com_ptr_t](../cpp/com-ptr-t-class.md)