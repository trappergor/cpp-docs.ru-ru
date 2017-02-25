---
title: "/Zc:strictStrings (отключение преобразования типов строковых литералов) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/Zc:strictStrings"
  - "strictStrings"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc - параметры компилятора (C++)"
  - "/Zc:strictStrings"
  - "strictStrings"
  - "Zc - параметры компилятора (C++)"
  - "-Zc - параметры компилятора (C++)"
ms.assetid: b7eb3f3b-82c1-48a2-8e63-66bad7397b46
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /Zc:strictStrings (отключение преобразования типов строковых литералов)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Если этот параметр указан, компилятор требует строгого соответствия `const`\-квалификации для указателей, инициализированных с помощью строковых литералов.  
  
## Синтаксис  
  
```  
/Zc:strictStrings[-]  
```  
  
## Заметки  
 Если указан параметр **\/Zc:strictStrings**, компилятор принудительно применяет стандартные квалификаторы `const` C\+\+ к строковым литералам, например "array of `const` `char`" или "array of `const` `wchar_t`", в зависимости от объявления.  Строковые литералы являются неизменяемыми, и при попытке изменения содержимого одного из них возникает ошибка нарушения доступа во время выполнения.  Необходимо объявить указатель на строку как указатель `const`, чтобы инициализировать его с помощью строкового литерала, или использовать явное приведение `const_cast` для инициализации указателя, не являющегося указателем `const`.  По умолчанию или если указан параметр **\/Zc:strictStrings\-**, компилятор не применяет принудительно стандартные квалификаторы `const` C\+\+ для указателей на строки, инициализированных строковыми литералами.  
  
 Используйте параметр **\/Zc:strictStrings**, чтобы предотвратить компиляцию неверного кода.  В этом примере демонстрируется, как простая ошибка объявления приводит к сбою во время выполнения.  
  
```cpp  
// strictStrings_off.cpp  
// compile by using: cl /W4 strictStrings_off.cpp  
int main() {  
   wchar_t* str = L"hello";  
   str[2] = L'a'; // run-time error: access violation  
}  
```  
  
 Если параметр **\/Zc:strictStrings** включен, для этого же кода выводится сообщение об ошибке в объявлении `str`.  
  
```cpp  
// strictStrings_on.cpp  
// compile by using: cl /Zc:strictStrings /W4 strictStrings_on.cpp  
int main() {  
   wchar_t* str = L"hello"; // error: Conversion from string literal   
   // loses const qualifier  
   str[2] = L'a';   
}  
```  
  
 При использовании `auto` для объявления указателя на строку компилятор автоматически создает правильное объявление типа указателя `const`.  О попытке изменить содержимое указателя `const` компилятор сообщает как об ошибке.  
  
> [!NOTE]
>  Стандартная библиотека C\+\+ в [!INCLUDE[cpp_dev12_long](../../build/reference/includes/cpp_dev12_long_md.md)] не поддерживает параметр компилятора **\/Zc:strictStrings** при отладочной сборке.  Если в выходных данных сборки присутствует несколько ошибок [C2665](../../error-messages/compiler-errors-2/compiler-error-c2665.md), это может быть причиной.  
  
 Подробнее о вопросах соответствия в Visual C\+\+ см. в статье [Нестандартное поведение](../Topic/Nonstandard%20Behavior.md).  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Работа со свойствами проектов](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **C\/C\+\+**.  
  
3.  Выберите страницу свойств **Командная строка**.  
  
4.  Измените свойство **Дополнительные параметры**, включив параметр `/Zc:strictStrings`, а затем нажмите кнопку **ОК**.  
  
## См. также  
 [\/Zc \(соответствие\)](../../build/reference/zc-conformance.md)