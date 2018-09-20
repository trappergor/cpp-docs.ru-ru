---
title: Дескриптор отслеживания для упакованных значений | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- boxed value types, tracking handle to
ms.assetid: 16c92048-5b74-47d5-8eca-dfea3d38879a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c7e26efae93b509700c3bb0c992d9f397559e99f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380736"
---
# <a name="a-tracking-handle-to-a-boxed-value"></a>Дескриптор отслеживания для упакованных значений

Использование дескриптор отслеживания для ссылки на тип значения отличается от управляемых расширений для C++ в Visual C++.

Упаковка-преобразование является особенностью CLR единой системы типов. Типы значений непосредственно содержат их состоянии, пока ссылочные типы представляют собой неявные пары: Именованная сущность — это дескриптор для неименованного объекта, размещенного в управляемой куче. Инициализации или присвоения значения типа `Object`, например, должны располагаться, тип значения в куче среды CLR - это создала изображение процесса упаковки его - сначала, выделив соответствующую память, а затем путем копирования состояние тип значения и затем возвращаясь адрес этот анонимный гибридного Справочник по значениям. Таким образом, при написании на C#

```cpp
object o = 1024; // C# implicit boxing
```

Нет, гораздо большую происходило чем может показаться, простота кода. Проект C# также упрощает не только то, какие операции выполняются за кулисами, но также абстракции самого процесса упаковки. Управляемых расширений для C++, с другой стороны, думать, что это может привести к ложное чувство эффективность, помещает его в пользователя лиц, требуя явные инструкции:

```cpp
Object *o = __box( 1024 ); // Managed Extensions explicit boxing
```

Упаковка является неявной в Visual C++:

```cpp
Object ^o = 1024; // new syntax implicit boxing
```

`__box` Ключевое слово выполняет очень важную функцию в управляемых расширениях, которая отсутствует языках, таких как C# и Visual Basic: оно предоставляет словарь и отслеживания дескриптор для непосредственного управления упакованного экземпляра в управляемой куче. Например рассмотрим следующую небольшую программу:

```cpp
int main() {
   double result = 3.14159;
   __box double * br = __box( result );

   result = 2.7;
   *br = 2.17;
   Object * o = br;

   Console::WriteLine( S"result :: {0}", result.ToString() ) ;
   Console::WriteLine( S"result :: {0}", __box(result) ) ;
   Console::WriteLine( S"result :: {0}", br );
}
```

Базовый код, созданный для трех вызовов функции `WriteLine` Показать различные уровни затрат на обращение к значению упакованное значение введите (спасибо Иву Дольче за указание на эти различия), где указанными строками Показать дополнительные издержки, связанные с каждым вызов.

```cpp
// Console::WriteLine( S"result :: {0}", result.ToString() ) ;
ldstr      "result :: {0}"
ldloca.s   result  // ToString overhead
call       instance string  [mscorlib]System.Double::ToString()  // ToString overhead
call       void [mscorlib]System.Console::WriteLine(string, object)

// Console::WriteLine( S"result :: {0}", __box(result) ) ;
Ldstr    " result :: {0}"
ldloc.0
box    [mscorlib]System.Double // box overhead
call    void [mscorlib]System.Console::WriteLine(string, object)

// Console::WriteLine( S"result :: {0}", br );
ldstr    "result :: {0}"
ldloc.0
call     void [mscorlib]System.Console::WriteLine(string, object)
```

Передавать тип упакованного значения непосредственно в `Console::WriteLine` исключает упаковки-преобразования и необходимость вызова `ToString()`. (Конечно, существует более ранняя упаковка-преобразование для инициализации `br`, чтобы извлечь выгоду, необходимо использовать `br` для работы.

В новом синтаксисе поддержка упакованных типов значений гораздо более элегантной и интегрируется в систему типов, сохраняя его мощности. Например вот перевод ранее небольшой программы:

```cpp
int main()
{
   double result = 3.14159;
   double^ br = result;
   result = 2.7;
   *br = 2.17;
   Object^ o = br;
   Console::WriteLine( "result :: {0}", result.ToString() );
   Console::WriteLine( "result :: {0}", result );
   Console::WriteLine( "result :: {0}", br );
}
```

## <a name="see-also"></a>См. также

[Типы значений и их режимы работы (C++/CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)<br/>
[Практическое руководство. Явный запрос упаковки-преобразования](../dotnet/how-to-explicitly-request-boxing.md)