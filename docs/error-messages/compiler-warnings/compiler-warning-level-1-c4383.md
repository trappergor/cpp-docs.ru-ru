---
title: "Предупреждение компилятора (уровень 1) C4383 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4383"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4383"
ms.assetid: 96c0e52d-874e-4b57-a154-0e49b6a00fae
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Предупреждение компилятора (уровень 1) C4383
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"оператор\_разыменовывания\_экземпляра" : значение разыменовывания дескриптора может измениться, если существует определенный пользователем оператор "оператор"; запишите оператор как статическую функцию, чтобы операнд был задан явно  
  
 Если добавляется пользовательское переопределение экземпляра для оператора разыменовывания в управляемом типе, то потенциально переопределяется возможность возвращения объекта дескриптора оператором разыменовывания типа.  Рекомендуется рассмотреть возможность написания статического пользовательского оператора.  
  
 Дополнительные сведения см. в разделах [Оператор дескриптора объекта \(^\)](../../windows/handle-to-object-operator-hat-cpp-component-extensions.md) и [Оператор отслеживания ссылок](../../windows/tracking-reference-operator-cpp-component-extensions.md).  
  
 Кроме того, оператор экземпляра недоступен для компиляторов других языков через метаданные, на которые существуют ссылки.  Для получения дополнительной информации см. [Пользовательские операторы](../../dotnet/user-defined-operators-cpp-cli.md).  
  
## Пример  
 Следующий пример приводит к возникновению предупреждения C4383.  
  
```  
// C4383.cpp  
// compile with: /clr /W1  
  
ref struct S {  
   int operator*() { return 0; }   // C4383  
};  
  
ref struct T {  
   static int operator*(T%) { return 0; }  
};   
  
int main() {  
   S s;  
   S^ pS = %s;  
  
   T t;  
   T^ pT = %t;  
   T% rT = *pT;  
}  
```