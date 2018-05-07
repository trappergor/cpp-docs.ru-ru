---
title: Ошибка средств компоновщика LNK1256 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- xml
- LNK1256
dev_langs:
- C++
helpviewer_keywords:
- LNK1256
ms.assetid: 55b64b2b-a56b-436c-a55e-ec9c6dcb050e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e4039dccb4dc8abd421b4622bbe928931f7f396
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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