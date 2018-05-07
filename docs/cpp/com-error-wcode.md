---
title: _com_error::WCode | Документы Microsoft
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
ms.openlocfilehash: 1354d490446795e55b41fa0c548e8dd8aa38c71b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="comerrorwcode"></a>_com_error::WCode
**Блок, относящийся только к системам Microsoft**  
  
 Извлекает 16-битный код ошибки, сопоставленный инкапсулированному значению `HRESULT`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
WORD WCode ( ) const throw( );  
  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если `HRESULT` находится в пределах диапазона от 0x80040200 до 0x8004FFFF **WCode** возвращает `HRESULT` минус 0x80040200; в противном случае возвращается ноль.  
  
## <a name="remarks"></a>Примечания  
 **WCode** метод используется для отмены сопоставления, выполняемого в коде поддержки COM. Программа-оболочка для **disp-интерфейса** свойство или метод вызывает вспомогательную процедуру, которая упаковывает аргументы и вызывает **IDispatch::Invoke**. Если сбой при возврате `HRESULT` из `DISP_E_EXCEPTION` возвращается, сведения об ошибках извлекаются из **EXCEPINFO** структуры передается **IDispatch::Invoke**. Код ошибки может быть 16-разрядное значение, хранящееся в `wCode` членом **EXCEPINFO** или полным 32-разрядным значением в **scode** членом **EXCEPINFO**структуры. Если возвращен 16-разрядный код `wCode`, его необходимо сначала сопоставить 32-разрядному коду сбоя `HRESULT`.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)   
 [_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)   
 [Класс _com_error](../cpp/com-error-class.md)