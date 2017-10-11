---
title: "Классы поддержки компилятора COM | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_raise_error
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 6d800d9b-b902-4033-9639-740a30b06f88
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 48540910db97e7662eeaa7e8a7febf7e44df653b
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="compiler-com-support-classes"></a>Классы поддержки компилятора COM
**Блок, относящийся только к системам Майкрософт**  
  
 Стандартные классы используются для поддержки некоторых типов модели COM. Классы определены в файле comdef.h и являются файлами заголовка, созданными из библиотеки типов.  
  
|Класс|Назначение|  
|-----------|-------------|  
|[_bstr_t](../cpp/bstr-t-class.md)|Создает программу оболочку для типа `BSTR`, предоставляя полезные операторы и методы.|  
|[_com_error](../cpp/com-error-class.md)|Определяет объект ошибки, вызванные [_com_raise_error](../cpp/com-raise-error.md) в случае большинства сбоев.|  
|[_com_ptr_t](../cpp/com-ptr-t-class.md)|Инкапсулирует указатели COM-интерфейса и автоматически выполняет необходимые вызовы методов `AddRef`, **выпуска**, и `QueryInterface`.|  
|[_variant_t](../cpp/variant-t-class.md)|Создает оболочку для **VARIANT** типа, предоставляя полезные операторы и методы.|  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Поддержка COM компилятора](../cpp/compiler-com-support.md)   
 [Глобальные функции COM компилятора](../cpp/compiler-com-global-functions.md)   
 [Справочник по языку C++](../cpp/cpp-language-reference.md)
