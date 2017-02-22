---
title: "Ошибка средств компоновщика LNK2031 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2031"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2031"
ms.assetid: 18ed4b6e-3e75-443c-bbd8-2f6030dc89ee
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ошибка средств компоновщика LNK2031
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

не удается создать p\/invoke для "function\_declaration" decorated\_name; соглашение о вызове отсутствует в метаданных  
  
 При попытке импортирования внутренней функции в чистый образ следует помнить о том, что явный вызов соглашений отличается во внутренней и чистой компиляции.  Дополнительные сведения о "чистых" образах см. в разделе [Чистый и проверяемый код](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
## Пример  
 В примере этого кода создается компонент с экспортированной и внутренней функцией, явно вызывающий соглашение [\_\_cdecl](../Topic/__cdecl.md).  
  
```  
// LNK2031.cpp  
// compile with: /LD  
extern "C" {  
   __declspec(dllexport) int func() { return 3; }  
};  
```  
  
## Пример  
 В следующем примере создается чистый клиент, использующий внутреннюю функцию.  Однако вызов соглашения в **\/clr:pure** представляет из себя [\_\_clrcall](../../cpp/clrcall.md).  В следующем примере формируется сообщение об ошибке LNK2031.  
  
```  
// LNK2031_b.cpp  
// compile with: /clr:pure LNK2031.lib  
// LNK2031 expected  
extern "C" int func();  
  
int main() {  
   return func();  
}  
```  
  
## Пример  
 В следующем примере показано, как использовать внутреннюю функцию для чистого образа.  Обратите внимание на явный вызов описателя соглашения **\_\_cdecl**.  
  
```  
// LNK2031_c.cpp  
// compile with: /clr:pure LNK2031.lib  
extern "C" int __cdecl func();  
  
int main() {  
   return func();  
}  
```