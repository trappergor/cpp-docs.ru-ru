---
title: "Платформа, default и cli пространства имен (расширения компонентов C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- lang
- cli
dev_langs: C++
helpviewer_keywords:
- lang namespace
- cli namespace
ms.assetid: 9d38bd1e-dc78-47d1-a84b-9b4683e52c9c
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5e5fa26b46a110fd59f7568a9101270766928f89
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="platform-default-and-cli-namespaces--c-component-extensions"></a>Пространства имен platform, default и cli (расширения компонентов C++)
Пространство имен определяет имена языковых элементов таким образом, чтобы они не конфликтовали с именами в других частях исходного кода, которые в противном случае считались бы идентичными. Например, конфликт имен может запретить компилятору выполнять распознавание [контекстно-зависимые ключевые слова](../windows/context-sensitive-keywords-cpp-component-extensions.md). Пространства имен используются компилятором, но не сохраняются в скомпилированной сборке.  
  
## <a name="all-runtimes"></a>Все среды выполнения  
 При создании проекта Visual C++ предоставляет для него пространство имен по умолчанию. Можно вручную переименовать пространство имен, несмотря на то, что в среде выполнения Windows имя winmd-файла должно соответствовать имени корневого пространства имен.  
  
## <a name="windows-runtime"></a>Среда выполнения Windows  
 Дополнительные сведения см. в разделе [пространства имен и видимость типов (C + +/ CX)](http://msdn.microsoft.com/library/windows/apps/hh969551.aspx).  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/ZW**  
  
## <a name="common-language-runtime"></a>Среда CLR 
 **Синтаксис**  
  
```  
using namespace cli;  
```  
  
 **Заметки**  
  
 C + +/ CLI поддерживает `cli` пространства имен. При компиляции с параметром **/CLR**, `using` подразумевается инструкции в разделе "синтаксис".  
  
 Следующие функции языка находятся в пространстве имен `cli`:  
  
-   [Массивы](../windows/arrays-cpp-component-extensions.md)  
  
-   [interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)  
  
-   [pin_ptr (C++/CLI)](../windows/pin-ptr-cpp-cli.md)  
  
-   [safe_cast](../windows/safe-cast-cpp-component-extensions.md)  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/clr**  
  
### <a name="examples"></a>Примеры  
 **Пример**  
  
 В следующем примере кода показано, что можно использовать символ в пространстве имен `cli` в качестве определяемого пользователем символа в коде.  Однако сделав это, необходимо будет явно или неявно определить ссылки на языковой элемент `cli` с таким же именем.  
  
```  
// cli_namespace.cpp  
// compile with: /clr  
using namespace cli;  
int main() {  
   array<int> ^ MyArray = gcnew array<int>(100);  
   int array = 0;  
  
   array<int> ^ MyArray2 = gcnew array<int>(100);   // C2062  
  
   // OK  
   cli::array<int> ^ MyArray2 = gcnew cli::array<int>(100);  
   ::array<int> ^ MyArray3 = gcnew ::array<int>(100);  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)