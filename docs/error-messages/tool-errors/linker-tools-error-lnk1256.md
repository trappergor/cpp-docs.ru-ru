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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bbbb14e4f4fdef63b58bdef5ecafcfe0b045f412
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1256"></a>Ошибка средств компоновщика LNK1256
Ошибка операции ALINK : причина  
  
 Наиболее частая причина LNK1256 — неверный номер версии сборки. Значение 65535 не может быть использовано в любой части номера версии сборки. Допустимый диапазон версий сборок: 0 - 65534.  
  
 LNK1256 может возникнуть в случае, если ALINK не удается найти именованный контейнер ключа. Удалить контейнер ключей и добавьте ее снова для строгого имени поставщика служб Шифрования с помощью [Sn.exe (средство строгих имен)](/dotnet/framework/tools/sn-exe-strong-name-tool).  
  
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