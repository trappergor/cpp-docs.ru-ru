---
title: Глобальные функции COM компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 74449d26-50a2-47c7-b175-7cf2cf83533e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4116d82ef38d7aaab29fe682e0881ac2e2ff5903
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32412193"
---
# <a name="compiler-com-global-functions"></a>Глобальные функции COM-модели компилятора
**Блок, относящийся только к системам Microsoft**  
  
 Доступны следующие процедуры.  
  
|Функция|Описание|  
|--------------|-----------------|  
|[_com_raise_error](../cpp/com-raise-error.md)|Создает [_com_error](../cpp/com-error-class.md) в ответ на ошибку.|  
|[_set_com_error_handler](../cpp/set-com-error-handler.md)|Заменяет функцию по умолчанию, используемую для обработки ошибок COM.|  
|[ConvertBSTRToString](../cpp/convertbstrtostring.md)|Преобразует `BSTR` значение **char \*** .|  
|[ConvertStringToBSTR](../cpp/convertstringtobstr.md)|Преобразует **char \***  значение `BSTR`.|  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Классы поддержки компилятора COM](../cpp/compiler-com-support-classes.md)   
 [Поддержка COM компилятора](../cpp/compiler-com-support.md)