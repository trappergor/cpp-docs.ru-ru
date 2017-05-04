---
title: "Перечисления (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 99fbbe28-c1cd-43af-9ead-60f90eba6e68
caps.latest.revision: 14
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 14
---
# Перечисления (C++/CX)
[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] поддерживает ключевое слово `public enum class`, которое аналогично стандартному ключевому слову `scoped  enum` в языке C\+\+. При использовании перечислителя, объявленного с помощью ключевого слова `public enum class`, необходимо использовать идентификатор перечисления, чтобы определить область каждого значения перечислителя.  
  
## Примечания  
 Объявление `public enum class`, не содержащее спецификатор доступа, например `public`, обрабатывается как стандартное [перечисление С\+\+ с областью видимости](~/cpp/enumerations-cpp.md).  
  
 Объявление `public enum class` или `public enum struct` может иметь базовый тип любого целочисленного типа, хотя для [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] необходимо, чтобы для перечислений флагов использовался тип int32 или uint32. Следующий синтаксис описывает части объявления `public enum class` или `public enum struct`. Дополнительные сведения см. в разделе [класс перечисления](~/windows/enum-class-cpp-component-extensions.md).  
  
 В этом примере показано, как определить открытый класс перечисления:  
  
 [!code-cpp[cx_enums#01](../snippets/cpp/VS_Snippets_Misc/cx_enums/cpp/class1.h#01)]  
  
 В следующем примере показано, как использовать его:  
  
 [!code-cpp[cx_enums#02](../snippets/cpp/VS_Snippets_Misc/cx_enums/cpp/class1.h#02)]  
  
## Примеры  
 В следующих примерах показано, как объявить перечисление.  
  
 [!code-cpp[cx_enums#03](../snippets/cpp/VS_Snippets_Misc/cx_enums/cpp/class1.h#03)]  
  
 В следующем примере показано, как выполнять приведение к числовым эквивалентами и выполнять сравнения. Обратите внимание, что область использования перечислителя `One` определяется идентификатором перечисления `Enum1`, а область использования перечислителя `First` — идентификатором `Enum2`.  
  
 [!code-cpp[cx_enums#04](../snippets/cpp/VS_Snippets_Misc/cx_enums/cpp/class1.h#04)]  
  
## См. также  
 [Система типов](../cppcx/type-system-c-cx.md)   
 [Справочник по языку C\+\+](../cppcx/visual-c-language-reference-c-cx.md)   
 [Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)