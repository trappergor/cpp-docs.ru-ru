---
title: "Оператор __uuidof | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__LIBID_"
  - "__LIBID_cpp"
  - "__uuidof"
  - "__uuidof_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__LIBID_ - ключевое слово [C++]"
  - "__uuidof - ключевое слово [C++]"
ms.assetid: badfe709-809b-4b66-ad48-ee35039d25c6
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор __uuidof
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Извлекает идентификатор GUID, присоединенный к выражению.  
  
## Синтаксис  
  
```  
  
      __uuidof (  
   expression   
)  
```  
  
## Заметки  
 Выражение \(*expression*\) может представлять собой имя типа, указатель, ссылку или массив этого типа, шаблон, специализированный для этого типа, или переменную этого типа.  Этот аргумент является допустимым, если компилятор может использовать его для поиска прикрепленного GUID.  
  
 Возможна особая ситуация, когда в качестве аргумента передается значение **0** или **NULL**.  В этом случае оператор `__uuidof` возвращает GUID, состоящий из нулей.  
  
 Это ключевое слово позволяет извлечь GUID, прикрепленный к следующим объектам:  
  
-   Объект, заданный расширенным атрибутом [uuid](../cpp/uuid-cpp.md).  
  
-   Блок библиотеки, созданный с атрибутом [module](../windows/module-cpp.md).  
  
> [!NOTE]
>  В отладочной сборке ключевое слово `__uuidof` всегда инициализирует объект динамически \(во время выполнения\).  В сборке выпуска ключевое слово `__uuidof` может инициализировать объект статически \(во время компиляции\).  
  
## Пример  
 Следующий код \(скомпилированный с библиотекой ole32.lib\) будет выводить идентификатор uuid для блока библиотеки, созданного с атрибутом module.  
  
```  
// expre_uuidof.cpp  
// compile with: ole32.lib  
#include "stdio.h"  
#include "windows.h"  
  
[emitidl];  
[module(name="MyLib")];  
[export]  
struct stuff {  
   int i;  
};  
  
int main() {  
   LPOLESTR lpolestr;  
   StringFromCLSID(__uuidof(MyLib), &lpolestr);  
   wprintf_s(L"%s", lpolestr);  
   CoTaskMemFree(lpolestr);  
}  
```  
  
## Комментарии  
 В случаях, когда имя библиотеки исключено из области видимости, вместо ключевого слова `__uuidof` можно использовать \_\_LIBID\_.  Например:  
  
```  
StringFromCLSID(__LIBID_, &lpolestr);  
```  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Выражения с унарными операторами](../Topic/Expressions%20with%20Unary%20Operators.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)