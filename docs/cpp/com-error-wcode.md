---
title: _com_error::WCode | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::WCode
dev_langs:
- C++
helpviewer_keywords:
- WCode method [C++]
ms.assetid: f3b21852-f8ea-4e43-bff1-11c2d35454c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: da4ad7d7f06c9cb6ae1a75a4c17cc63b377a9845
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036518"
---
# <a name="comerrorwcode"></a>_com_error::WCode

**Блок, относящийся только к системам Microsoft**

Получает код ошибки 16-разрядное, сопоставленный в инкапсулированном виде HRESULT.

## <a name="syntax"></a>Синтаксис

```
WORD WCode ( ) const throw( );
```

## <a name="return-value"></a>Возвращаемое значение

Если значение HRESULT равно в пределах диапазона от 0x80040200 до 0x8004FFFF, `WCode` метод возвращает значение HRESULT минус 0x80040200; в противном случае возвращается ноль.

## <a name="remarks"></a>Примечания

`WCode` Метод используется для отмены сопоставления, происходит в коде поддержки COM. Программы-оболочки для `dispinterface` свойства или метода вызывает вспомогательную процедуру, которая упаковывает аргументы и вызывает `IDispatch::Invoke`. Если значение HRESULT при возврате из `DISP_E_EXCEPTION` возвращается, сведения об ошибке извлекается из `EXCEPINFO` структуры передается `IDispatch::Invoke`. Код ошибки может быть 16-разрядное значение, хранящееся в `wCode` членом `EXCEPINFO` структуры или значение в 32-разрядных `scode` членом `EXCEPINFO` структуры. Если 16-разрядное `wCode` возвращается, его необходимо сначала сопоставить 32-разрядных ошибку HRESULT.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)<br/>
[_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)<br/>
[Класс _com_error](../cpp/com-error-class.md)