---
title: "Ошибка средств компоновщика LNK1237 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1237"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1237"
ms.assetid: 8722ffa8-096a-4bb0-85f9-f3aa0e10872a
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Ошибка средств компоновщика LNK1237
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

при создании кода компилятор ввел ссылку на символ "символ", определенный в модуле "модуль", откомпилированном с параметром \/GL  
  
 Во время создания кода компилятор не должен вводить символы, которые позднее разрешаются в скомпилированных определениях **\/GL**.  `symbol` — это символ, введенный и позднее разрешенный для определения, скомпилированного с **\/GL**.  
  
 Для получения дополнительной информации см. [\/GL \(оптимизация всей программы\)](../../build/reference/gl-whole-program-optimization.md).  
  
 Чтобы устранить ошибку LNK1237, не компилируйте символ с параметром **\/GL** и не используйте параметр [\/INCLUDE \(принудительные ссылки на символы\)](../../build/reference/include-force-symbol-references.md) для принудительного создания ссылки на символ.  
  
## Пример  
 В следующем примере возникает ошибка LNK1237.  Чтобы устранить эту ошибку, не инициализируйте массив в файле LNK1237\_a.cpp и добавьте параметр **\/include:\_\_chkstk** к команде link.  
  
```  
// LNK1237_a.cpp  
int main() {  
   char c[5000] = {0};  
}  
```  
  
```  
// LNK1237_b.cpp  
// compile with: /GS- /GL /c LNK1237_a.cpp  
// processor: x86  
// post-build command: (lib LNK1237_b.obj /LTCG & link LNK1237_a.obj LNK1237_b.lib /nodefaultlib /entry:main /LTCG)  
extern "C" void _chkstk(size_t s) {}  
```