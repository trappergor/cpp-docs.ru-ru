---
title: __identifier (c + +/ CLI) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- __identifier
- __identifier_cpp
dev_langs:
- C++
helpviewer_keywords:
- __identifier keyword [C++]
ms.assetid: 348428af-afa7-4ff3-b571-acf874301cf2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a96363fcfbc753e727c6cbb6a5efbbb5606b6c40
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="identifier-ccli"></a>__identifier (C++/CLI)
Включает использование ключевых слов Visual C++ в качестве идентификаторов.  
  
## <a name="all-platforms"></a>Все платформы  
**Синтаксис**  
  
```  
__identifier(  
Visual_C++_keyword  
)  
  
```  
  
**Заметки**  
  
Использование `__identifier` ключевое слово для идентификаторов, которые не являются ключевыми словами, разрешено, но настоятельно не рекомендуется, как правило стиля.  
  
## <a name="windows-runtime"></a>Среда выполнения Windows  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/ZW**  
  
### <a name="examples"></a>Примеры  
 **Пример**  
  
 В следующем примере класс с именем `template` создается в C# и распространяемых в виде библиотеки DLL. В программе Visual C++, которая использует `template` класса `__identifier` ключевое слово скрывает тот факт, `template` является ключевым словом standard C++.  
  
```  
// identifier_template.cs  
// compile with: /target:library  
public class template {  
   public void Run() { }  
}  
```  
  
```  
// keyword__identifier.cpp  
// compile with: /ZW  
#using <identifier_template.dll>  
int main() {  
   __identifier(template)^ pTemplate = ref new __identifier(template)();  
   pTemplate->Run();  
}  
```  
  
## <a name="common-language-runtime"></a>Среда CLR 
 **Заметки**  
  
 `__identifier` Ключевое слово может использоваться с **/CLR** параметр компилятора.  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/clr**  
  
### <a name="examples"></a>Примеры  
 **Пример**  
  
 В следующем примере класс с именем `template` создается в C# и распространяемых в виде библиотеки DLL. В программе Visual C++, которая использует `template` класса `__identifier` ключевое слово скрывает тот факт, `template` является ключевым словом standard C++.  
  
```  
// identifier_template.cs  
// compile with: /target:library  
public class template {  
   public void Run() { }  
}  
```  
  
```  
// keyword__identifier.cpp  
// compile with: /clr  
#using <identifier_template.dll>  
  
int main() {  
   __identifier(template) ^pTemplate = gcnew __identifier(template)();  
   pTemplate->Run();  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)   
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)