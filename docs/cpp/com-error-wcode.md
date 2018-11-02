---
title: _com_error::WCode
ms.date: 11/04/2016
f1_keywords:
- _com_error::WCode
helpviewer_keywords:
- WCode method [C++]
ms.assetid: f3b21852-f8ea-4e43-bff1-11c2d35454c4
ms.openlocfilehash: f33871634b516723c94fead847f64ef20d25513f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50620978"
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