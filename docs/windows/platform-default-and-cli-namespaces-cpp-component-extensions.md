---
title: "Пространства имен platform, default и cli (расширения компонентов C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "lang"
  - "cli"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cli - пространство имен"
  - "lang - пространство имен"
ms.assetid: 9d38bd1e-dc78-47d1-a84b-9b4683e52c9c
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Пространства имен platform, default и cli (расширения компонентов C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Пространство имен определяет имена языковых элементов таким образом, чтобы они не конфликтовали с именами в других частях исходного кода, которые в противном случае считались бы идентичными.  Например, конфликты имен могут не дать компилятору распознать [Контекстные ключевые слова](../windows/context-sensitive-keywords-cpp-component-extensions.md).  Пространства имен используются компилятором, но не сохраняются в скомпилированной сборке.  
  
## Все среды выполнения  
 При создании проекта Visual C\+\+ предоставляет для него пространство имен по умолчанию.  Можно вручную переименовать пространство имен, хотя в [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] имя WINMD\-файла должно соответствовать имени корневого пространства имен.  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 Дополнительные сведения см. в разделе [Пространства имен и видимость типов \(C\+\+\/CX\)](http://msdn.microsoft.com/library/windows/apps/hh969551.aspx).  
  
### Требования  
 Параметр компилятора: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Синтаксис**  
  
```  
using namespace cli;  
```  
  
 **Примечания**  
  
 [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)] поддерживает пространство имен `cli`.  При компиляции с помощью **\/clr** в разделе синтаксиса используется оператор `using`.  
  
 Следующие функции языка находятся в пространстве имен `cli`:  
  
-   [Массивы](../windows/arrays-cpp-component-extensions.md)  
  
-   [interior\_ptr \(C\+\+\/CLI\)](../windows/interior-ptr-cpp-cli.md)  
  
-   [pin\_ptr \(C\+\+\/CLI\)](../Topic/pin_ptr%20\(C++-CLI\).md)  
  
-   [safe\_cast](../windows/safe-cast-cpp-component-extensions.md)  
  
### Требования  
 Параметр компилятора: **\/clr**  
  
### Примеры  
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
  
## См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)