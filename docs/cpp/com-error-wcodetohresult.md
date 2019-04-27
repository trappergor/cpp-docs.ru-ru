---
title: _com_error::WCodeToHRESULT
ms.date: 11/04/2016
f1_keywords:
- _com_error::WCodeToHRESULT
helpviewer_keywords:
- WCodeToHRESULT method [C++]
ms.assetid: 0ec43a4b-ca91-42d5-b270-3fde9c8412ea
ms.openlocfilehash: f2fc84be53d95754d21c30eaea8dd981447453d6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154933"
---
# <a name="comerrorwcodetohresult"></a>_com_error::WCodeToHRESULT

**Блок, относящийся только к системам Microsoft**

Сопоставляет 16-разрядный *wCode* 32-разрядное значение HRESULT.

## <a name="syntax"></a>Синтаксис

```
static HRESULT WCodeToHRESULT(
   WORD wCode
) throw( );
```

#### <a name="parameters"></a>Параметры

*WCode*<br/>
16-разрядный *wCode* сопоставляться с 32-разрядное значение HRESULT.

## <a name="return-value"></a>Возвращаемое значение

32-разрядное значение HRESULT, сопоставленное с 16-разрядной *wCode*.

## <a name="remarks"></a>Примечания

См. в разделе [WCode](../cpp/com-error-wcode.md) функция-член.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[_com_error::WCode](../cpp/com-error-wcode.md)<br/>
[_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)<br/>
[Класс _com_error](../cpp/com-error-class.md)