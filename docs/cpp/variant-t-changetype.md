---
title: _variant_t::ChangeType
ms.date: 11/04/2016
f1_keywords:
- _variant_t::ChangeType
- _variant_t.ChangeType
helpviewer_keywords:
- ChangeType method [C++]
- VARIANT object [C++], ChangeType
- VARIANT object
ms.assetid: 829d2eeb-3338-4a88-9dce-0ca145f47aac
ms.openlocfilehash: b0692c9befaa6b7e787ada624dcbb56b074c9f9d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80160467"
---
# <a name="_variant_tchangetype"></a>_variant_t::ChangeType

**Блок, относящийся только к системам Microsoft**

Изменяет тип объекта `_variant_t` на указанный `VARTYPE`.

## <a name="syntax"></a>Синтаксис

```
void ChangeType(
   VARTYPE vartype,
   const _variant_t* pSrc = NULL
);
```

#### <a name="parameters"></a>Параметры

*VarType*<br/>
`VARTYPE` для этого `_variant_t` объекта.

*pSrc*<br/>
Указатель на объект `_variant_t`, который необходимо преобразовать. Если это значение равно NULL, преобразование выполняется на месте.

## <a name="remarks"></a>Remarks

Эта функция-член преобразует объект `_variant_t` в указанное `VARTYPE`. Если *pSrc* имеет значение null, преобразование выполняется на месте, в противном случае объект `_variant_t` копируется из *pSrc* и затем преобразуется.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Класс _variant_t](../cpp/variant-t-class.md)
