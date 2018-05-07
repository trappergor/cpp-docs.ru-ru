---
title: Предупреждение средств компоновщика LNK4227 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4227
dev_langs:
- C++
helpviewer_keywords:
- LNK4227
ms.assetid: 941a0414-9964-4e02-8487-f9daa42ef7f9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b56617ee355654dfbb198252ea37cdb344950cf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4227"></a>Предупреждение средств компоновщика LNK4227  
  
> Предупреждение операции метаданных (*HRESULT*): *предупреждающее_сообщение*  
  
Компоновщик обнаружил различия в метаданных при слиянии:  
  
-   Один или несколько ссылочных сборок с сборка, построенная в настоящее время.  
  
-   Один или несколько файлов исходного кода при компиляции.  
  
Например, LNK4227 может появиться при наличии двух глобальных функций с одинаковыми именами, но объявить иначе, сведения о параметрах (то есть объявления не являются согласованными во всех компилируемых объектах). Используйте ildasm.exe/Text/Metadata *object_file* на каждый OBJ-файл, чтобы увидеть, как типы различаются.  
  
LNK4227 также позволяет сообщать о проблемах, возникших с помощью другого средства. Поиск предупреждение для получения дополнительной информации.  
  
Чтобы устранить это предупреждение, должны быть устранены проблемы с метаданными.  
  
## <a name="example"></a>Пример  
  
LNK4227 создается в том случае, когда ссылочной сборки был подписан иначе, чем в сборке, ссылающейся на него.  
  
Следующий пример приводит к возникновению ошибки LNK4227:  
  
```cpp  
// LNK4227.cpp  
// compile with: /clr  
using namespace System::Reflection;  
  
[assembly:AssemblyDelaySignAttribute(false)];  
  
int main() {}  
```  
  
 И потом  
  
```cpp  
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
  
## <a name="example"></a>Пример  
  
LNK4227 также может возникать, если атрибуты сборки передаются номера версий в неверном формате.  "*" Нотации относится только к `AssemblyVersionAttribute`.  Чтобы устранить это предупреждение, используйте только цифры в атрибутах версии отличный от `AssemblyVersionAttribute`.  
  
Следующий пример приводит к возникновению ошибки LNK4227:  
  
```cpp  
// LNK4227e.cpp  
// compile with: /clr /LD /W1  
using namespace System::Reflection;  
[assembly:AssemblyVersionAttribute("2.3.*")];   // OK  
[assembly:AssemblyFileVersionAttribute("2.3.*")];   // LNK4227  
// try the following line instead  
// [assembly:AssemblyFileVersionAttribute("2.3")];  
```