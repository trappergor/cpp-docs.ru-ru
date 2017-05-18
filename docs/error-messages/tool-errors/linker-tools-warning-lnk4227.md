---
title: "Предупреждение средств компоновщика LNK4227 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4227
dev_langs:
- C++
helpviewer_keywords:
- LNK4227
ms.assetid: 941a0414-9964-4e02-8487-f9daa42ef7f9
caps.latest.revision: 11
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
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: ee566318c7d19159f9a2c084d348b5010a65e2de
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-warning-lnk4227"></a>Предупреждение средств компоновщика LNK4227
Предупреждение операции метаданных (HRESULT): предупреждающее_сообщение  
  
Компоновщик обнаружил различия в метаданных при слиянии:  
  
-   Один или несколько ссылочных сборок с сборка, построенная в настоящее время.  
  
-   Один или несколько файлов исходного кода при компиляции.  
  
Например, LNK4227 может появиться при наличии двух глобальных функций с одинаковыми именами, но сведения о параметрах объявить иначе (объявления не являются согласованными во всех компилируемых объектах). Использовать ildasm.exe/Text/Metadata `object_file` на каждый .obj файла и увидеть отличия между типами.  
  
LNK4227 также сообщает о проблемах, инициированных другим инструментом. Например al.exe; в разделе [Al.exe ошибки и предупреждения средства](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b).  
  
Чтобы устранить это предупреждение, необходимо исправить проблемы с метаданными.  
  
Например LNK4227 создается, когда подписи иначе, чем сборка, ссылающаяся на его сборку.  
  
Следующий пример приводит к возникновению ошибки LNK4227:  
  
```  
// LNK4227.cpp  
// compile with: /clr  
using namespace System::Reflection;  
  
[assembly:AssemblyDelaySignAttribute(false)];  
  
int main() {}  
```  
  
 И потом  
  
```  
// LNK4227b.cpp  
// compile with: /clr LNK4227.cpp /FeLNK4227b.exe  
using namespace System::Reflection;  
using namespace System::Runtime::CompilerServices;  
  
[assembly:AssemblyDelaySignAttribute(true)];  
// Try the following line instead  
// [assembly:AssemblyDelaySignAttribute(false)];  
  
ref class MyClass  
{  
};  
```  
  
LNK4227 также может возникать, если атрибуты сборки передаются номера версий в неправильном формате.  ' *' Нотации относится к классу AssemblyVersionAttribute.  Чтобы устранить это предупреждение, используйте только номера версии атрибутов, отличных от AssemblyVersionAttribute.  
  
Следующий пример приводит к возникновению ошибки LNK4227:  
  
```  
// LNK4227e.cpp  
// compile with: /clr /LD /W1  
using namespace System::Reflection;  
[assembly:AssemblyVersionAttribute("2.3.*")];   // OK  
[assembly:AssemblyFileVersionAttribute("2.3.*")];   // LNK4227  
// try the following line instead  
// [assembly:AssemblyFileVersionAttribute("2.3")];  
```
