---
title: Глобальные функции COM компилятора | Документация Майкрософт
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
ms.openlocfilehash: aa138b045fcb5851a65b68d898b99a8cab269f6e
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402537"
---
# <a name="compiler-com-global-functions"></a>Глобальные функции COM-модели компилятора
**Блок, относящийся только к системам Microsoft**  
  
 Доступны следующие процедуры.  
  
|Функция|Описание:|  
|--------------|-----------------|  
|[_com_raise_error](../cpp/com-raise-error.md)|Создает [_com_error](../cpp/com-error-class.md) в ответ на сбой.|  
|[_set_com_error_handler](../cpp/set-com-error-handler.md)|Заменяет функцию по умолчанию, используемую для обработки ошибок COM.|  
|[ConvertBSTRToString](../cpp/convertbstrtostring.md)|Преобразует `BSTR` значение `char *`.|  
|[ConvertStringToBSTR](../cpp/convertstringtobstr.md)|Преобразует `char *` значение `BSTR`.|  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Классы поддержки компилятора COM](../cpp/compiler-com-support-classes.md)   
 [Поддержка COM компилятора](../cpp/compiler-com-support.md)