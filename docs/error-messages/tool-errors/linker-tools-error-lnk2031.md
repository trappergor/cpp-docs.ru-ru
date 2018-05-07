---
title: Ошибка средств компоновщика LNK2031 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2031
dev_langs:
- C++
helpviewer_keywords:
- LNK2031
ms.assetid: 18ed4b6e-3e75-443c-bbd8-2f6030dc89ee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 179702b3e162ad9f22fd887d60c5a5c2d0bc8559
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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