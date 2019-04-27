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
ms.openlocfilehash: 319c4fde808932e86021ee59b051261c43ca2edd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166208"
---
# <a name="varianttchangetype"></a>_variant_t::ChangeType

**Блок, относящийся только к системам Microsoft**

Изменяет тип `_variant_t` на указанный `VARTYPE`.

## <a name="syntax"></a>Синтаксис

```
void ChangeType(
   VARTYPE vartype,
   const _variant_t* pSrc = NULL
);
```

#### <a name="parameters"></a>Параметры

*VarType*<br/>
`VARTYPE` Для данного `_variant_t` объекта.

*pSrc*<br/>
Указатель на объект `_variant_t`, который необходимо преобразовать. Если это значение равно NULL, преобразование осуществляется на месте.

## <a name="remarks"></a>Примечания

Эта функция-член преобразует `_variant_t` объекта в указанный `VARTYPE`. Если *pSrc* имеет значение NULL, преобразование осуществляется на месте, в противном случае это `_variant_t` объект копируется из *pSrc* , а затем преобразуется.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _variant_t](../cpp/variant-t-class.md)