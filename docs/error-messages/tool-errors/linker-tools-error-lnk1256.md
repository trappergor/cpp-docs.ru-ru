---
title: "Ошибка средств компоновщика LNK1256 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- xml
- LNK1256
dev_langs:
- C++
helpviewer_keywords:
- LNK1256
ms.assetid: 55b64b2b-a56b-436c-a55e-ec9c6dcb050e
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 5e29e6100b57531c7a29f84e7c0feac53f20cec9
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

---
# <a name="linker-tools-error-lnk1256"></a>Ошибка средств компоновщика LNK1256
Ошибка операции ALINK : причина  
  
 Наиболее частая причина LNK1256 — неверный номер версии сборки. Значение 65535 не может быть использовано в любой части номера версии сборки. Допустимый диапазон версий сборок: 0 - 65534.  
  
 LNK1256 может возникнуть в случае, если ALINK не удается найти именованный контейнер ключа. Удалить контейнер ключей и добавьте ее снова для строгого имени поставщика служб Шифрования с помощью [Sn.exe (средство строгих имен)](http://msdn.microsoft.com/Library/c1d2b532-1b8e-4c7a-8ac5-53b801135ec6).  
  
 Еще одна возможная причина ошибки LNK1256 — несовпадение версий компоновщика и Alink.dll. Это может быть вызвано поврежденной установкой Visual Studio. Используйте **программы и компоненты** панели управления Windows для восстановления или переустановки Visual Studio.  
  
 Следующий пример приводит к возникновению ошибки LNK1256:  
  
```  
// LNK1256.cpp  
// compile with: /clr /LD  
// LNK1256 expected  
[assembly:System::Reflection::AssemblyVersionAttribute("1.0.65535")];  
public class CMyClass {  
public:  
   int value;  
};  
```
