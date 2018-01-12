---
title: "Ошибка средств компоновщика LNK2031 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2031
dev_langs: C++
helpviewer_keywords: LNK2031
ms.assetid: 18ed4b6e-3e75-443c-bbd8-2f6030dc89ee
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2a519b4241c9ffabaeeb387cc8e4997125d57781
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk2031"></a>Ошибка средств компоновщика LNK2031
не удалось создать p/invoke для decorated_name «function_declaration»; в метаданных отсутствует соглашение о вызовах  
  
 При попытке импортировать собственную функцию в чистом образе, следует помнить, что неявные соглашения о вызовах различаются внутренней и чистой компиляции. Дополнительные сведения об образах чисто см [чистый и проверяемый код (C + +/ CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
## <a name="example"></a>Пример  
 Этот пример кода приводит к возникновению ошибки компонента с экспортированного native, функции которого соглашение о вызовах является неявно [__cdecl](../../cpp/cdecl.md).  
  
```  
// LNK2031.cpp  
// compile with: /LD  
extern "C" {  
   __declspec(dllexport) int func() { return 3; }  
};  
```  
  
## <a name="example"></a>Пример  
 В следующем примере создается чистый клиент, использующий внутреннюю функцию. Тем не менее соглашение о вызовах в **/CLR: pure** — [__clrcall](../../cpp/clrcall.md). Следующий пример приводит к возникновению ошибки LNK2031.  
  
```  
// LNK2031_b.cpp  
// compile with: /clr:pure LNK2031.lib  
// LNK2031 expected  
extern "C" int func();  
  
int main() {  
   return func();  
}  
```  
  
## <a name="example"></a>Пример  
 Следующий пример показано, как использовать внутреннюю функцию для чистого образа. Обратите внимание на явный **__cdecl** вызов описателя соглашения.  
  
```  
// LNK2031_c.cpp  
// compile with: /clr:pure LNK2031.lib  
extern "C" int __cdecl func();  
  
int main() {  
   return func();  
}  
```