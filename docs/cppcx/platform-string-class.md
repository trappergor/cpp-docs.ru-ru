---
title: "Класс Platform::String | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String"
ms.assetid: 72dd04a4-a694-40d3-b899-eaa0b503eab8
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# Класс Platform::String
Представляет упорядоченную коллекцию символов Юникода, используемую для представления текста. Дополнительные сведения и примеры см. в разделе [Строки](../cppcx/strings-c-cx.md).  
  
## Синтаксис  
  
```cpp  
  
public ref class String sealed : Object,  
    IDisposable,  
    IEquatable,  
    IPrintable  
```  
  
## Итераторы  
 Две функции итераторов, не являющиеся членами класса String, можно использовать с функциями шаблона `std::for_each` для перечисления символов в объекте String.  
  
|Член|Описание|  
|----------|--------------|  
|`const char16* begin(String^ s)`|Возвращает указатель на начало указанного объекта String.|  
|`const char16* end(String^ s)`|Возвращает указатель на позицию после окончания указанного объекта String.|  
  
## Члены  
 Класс String наследует от класса Object и интерфейсов IDisposable, IEquatable и IPrintable.  
  
 Класс String имеет также следующие типы членов.  
  
 **Конструкторы**  
  
|Член|Описание|  
|----------|--------------|  
|[Конструктор String::String](../cppcx/string-string-constructor.md)|Инициализирует новый экземпляр класса String.|  
  
 **Методы**  
  
 Класс String наследует методы Equals\(\), Finalize\(\), GetHashCode\(\), GetType\(\), MemberwiseClose\(\) и ToString\(\) от класса [Класс Platform::Object](../cppcx/platform-object-class.md). Класс String содержит также следующие методы.  
  
|Метод|Описание|  
|-----------|--------------|  
|[Метод String::Begin](../cppcx/string-begin-method.md)|Возвращает указатель на начало текущей строки.|  
|[Метод String::CompareOrdinal](../cppcx/string-compareordinal-method.md)|Сравнивает два объекта `String`, оценивая числовые значения соответствующих символов в двух строковых значениях, представленных объектами.|  
|[Метод String::Concat](../cppcx/string-concat-method.md)|Объединяет значения двух объектов String.|  
|[Метод String::Data](../cppcx/string-data-method.md)|Возвращает указатель на начало текущей строки.|  
|[Метод String::Dispose](../cppcx/string-dispose-method.md)|Высвобождает ресурсы.|  
|[Метод String::End](../cppcx/string-end-method.md)|Возвращает указатель на позицию после конца текущей строки.|  
|[Метод String::Equals](../cppcx/string-equals-method.md)|Указывает, равен ли указанный объект текущему объекту.|  
|[Метод String::GetHashCode](../cppcx/string-gethashcode-method.md)|Возвращает хэш\-код данного экземпляра.|  
|[Метод String::IsEmpty](../cppcx/string-isempty-method.md)|Указывает, является ли объект String пустым.|  
|[Метод String::IsFastPass](../cppcx/string-isfastpass-method.md)|Указывает, участвует ли текущий объект String в операции *быстрой передачи*. В операции быстрой передачи подсчет ссылок приостанавливается.|  
|[Метод String::Length](../cppcx/string-length-method.md)|Получает длину текущего объекта String.|  
|[Метод String::ToString](../cppcx/string-tostring-method-c-cx.md)|Возвращает объект String, значение которого совпадает со значением текущей строки.|  
  
 **Свойства**  
  
 Класс String имеет следующие свойства.  
  
|Член|Описание|  
|----------|--------------|  
|[Оператор String::operator\=\=](../cppcx/string-operator-equality-operator-c-cx.md)|Указывает, равны ли значения двух указанных объектов String.|  
|[Оператор operator\+](../cppcx/string-operator-decrementoperator.md)|Сцепляет два объекта String в новый объект String.|  
|[Оператор String::operator\>](../cppcx/string-operator-greater-than-operator-c-cx.md)|Указывает, является ли значение одного объекта String большим, чем значение второго объекта String.|  
|[Оператор String::operator\>\=](../cppcx/string-operator-greater-than-or-equals-c-cx.md)|Указывает, является ли значение одного объекта String больше или равным значению второго объекта String.|  
|[Оператор String::operator\!\=](../cppcx/string-operator-inequality-operator-c-cx.md)|Указывает, различны ли значения двух указанных объектов String.|  
|[Оператор String::operator\<](../cppcx/string-operator-less-than-operator-c-cx.md)|Указывает, является ли значение одного объекта String меньшим, чем значение второго объекта String.|  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Заголовок** vccorlib.h \(включается по умолчанию\)  
  
## См. также  
 [Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)