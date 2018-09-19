---
title: _com_error::WCodeToHRESULT | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::WCodeToHRESULT
dev_langs:
- C++
helpviewer_keywords:
- WCodeToHRESULT method [C++]
ms.assetid: 0ec43a4b-ca91-42d5-b270-3fde9c8412ea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5b6712734cd7283558ad5776444586f8c0b3fa6e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077572"
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