---
title: Основные принципы использования управляемых исключений
ms.date: 11/04/2016
helpviewer_keywords:
- try-catch exception handling, managed applications
- __finally keyword, managed exceptions
- exceptions, managed
- try-catch exception handling
- catch blocks
- throwing exceptions, managed exceptions
- Visual C++, handling managed exceptions
ms.assetid: 40ce8931-1ecc-491a-815f-733b23fcba35
ms.openlocfilehash: 6bc1e9c6d40599ae9a821179dcf56dbb7e21bf10
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372531"
---
# <a name="basic-concepts-in-using-managed-exceptions"></a>Основные принципы использования управляемых исключений

В этой теме обсуждается обработка исключений в управляемых приложениях. То есть, приложение, которое компилируется с опцией компилятора **/clr.**

## <a name="in-this-topic"></a>В этом разделе

- [Метание исключения под /clr](#vcconbasicconceptsinusingmanagedexceptionsanchor1)

- [Попробуйте/Поймайте блоки для расширения CLR](#vcconbasicconceptsinusingmanagedexceptionsanchor2)

## <a name="remarks"></a>Remarks

Если компилировать с опцией **/clr,** можно обрабатывать исключения <xref:System.Exception> CLR, а также стандартный класс предоставляет много полезных методов для обработки исключений CLR и рекомендуется в качестве базового класса для классов исключений, определенных пользователем.

Поймать типы исключений, полученные из интерфейса, не поддерживается под **/clr.** Кроме того, время выполнения общего языка не позволяет поймать исключения переполнения стека; исключение переполнения стека завершает процесс.

Для получения дополнительной информации о различиях в обработке исключений в управляемых и неуправляемых приложениях [см.](../dotnet/differences-in-exception-handling-behavior-under-clr.md)

## <a name="throwing-exceptions-under-clr"></a><a name="vcconbasicconceptsinusingmanagedexceptionsanchor1"></a>Метание исключения под /clr

Выражение броска СЗ расширяется, чтобы бросить ручку типу CLR. Следующий пример создает пользовательский тип исключения, а затем бросает экземпляр этого типа:

```cpp
// clr_exception_handling.cpp
// compile with: /clr /c
ref struct MyStruct: public System::Exception {
public:
   int i;
};

void GlobalFunction() {
   MyStruct^ pMyStruct = gcnew MyStruct;
   throw pMyStruct;
}
```

Тип значения должен быть упакован перед бросиванием:

```cpp
// clr_exception_handling_2.cpp
// compile with: /clr /c
value struct MyValueStruct {
   int i;
};

void GlobalFunction() {
   MyValueStruct v = {11};
   throw (MyValueStruct ^)v;
}
```

## <a name="trycatch-blocks-for-clr-extensions"></a><a name="vcconbasicconceptsinusingmanagedexceptionsanchor2"></a>Попробуйте/Поймайте блоки для расширения CLR

Та же структура блока/**поймать** поймать может быть использована для ловли как CLR, так и родных исключений: **try**

```cpp
// clr_exception_handling_3.cpp
// compile with: /clr
using namespace System;
ref struct MyStruct : public Exception {
public:
   int i;
};

struct CMyClass {
public:
   double d;
};

void GlobalFunction() {
   MyStruct^ pMyStruct = gcnew MyStruct;
   pMyStruct->i = 11;
   throw pMyStruct;
}

void GlobalFunction2() {
   CMyClass c = {2.0};
   throw c;
}

int main() {
   for ( int i = 1; i >= 0; --i ) {
      try {
         if ( i == 1 )
            GlobalFunction2();
         if ( i == 0 )
            GlobalFunction();
      }
      catch ( CMyClass& catchC ) {
         Console::WriteLine( "In 'catch(CMyClass& catchC)'" );
         Console::WriteLine( catchC.d );
      }
      catch ( MyStruct^ catchException ) {
         Console::WriteLine( "In 'catch(MyStruct^ catchException)'" );
         Console::WriteLine( catchException->i );
      }
   }
}
```

### <a name="output"></a>Выходные данные

```
In 'catch(CMyClass& catchC)'
2
In 'catch(MyStruct^ catchException)'
11
```

### <a name="order-of-unwinding-for-c-objects"></a>Орден Раскручивания объектов СЗ

Раскручивание происходит для любых объектов СЗ с деструктором, которые могут находиться в стеке времени выполнения между функцией метания и функцией обработки. Поскольку типы CLR выделяются на куче, раскручивание не распространяется на них.

Порядок событий для брошенного исключения заключается в следующем:

1. Время выполнения ходит по стеку в поисках соответствующего положения о улове, или в случае SEH, за исключением фильтра для SEH, чтобы поймать исключение. Предложения по ловле ищутся сначала в лексическом порядке, а затем динамически вниз по стеку вызовов.

1. Как только правильный обработчик найден, стек раскручивается до этой точки. Для каждого вызова функции на стеке его локальные объекты разрушаются и __finally блоки выполняются из большинства вложенных наружу.

1. Как только стек раскручивается, оговорка catch выполняется.

### <a name="catching-unmanaged-types"></a>Поймать неуправляемые типы

При бросев неуправляемом типе объекта, <xref:System.Runtime.InteropServices.SEHException>он обернут за исключением типа. При поиске соответствующего положения **о улове** существует две возможности.

- При обнаружении родного типа СЗЗ исключение разворачивается и сравнивается с типом. Это сравнение позволяет ловить родной тип СЗЗ обычным способом.

- Однако, если пункт **о улове** типа **SEHException** или любой из его базовых классов рассматривается в первую очередь, оговорка перехватит исключение. Таким образом, вы должны поместить все положения улова, которые ловят родные типы C е, прежде чем любые положения о улове типов CLR.

Обратите внимание на следующее:

```
catch(Object^)
```

и

```
catch(...)
```

будет как поймать любой брошенный тип, включая исключения SEH.

Если неуправляемый тип пойман уловом (Объект), он не уничтожит брошенный объект.

При бросании или ловле неуправляемых исключений мы рекомендуем использовать опцию компилятора [/EHsc](../build/reference/eh-exception-handling-model.md) вместо **/EHs** или **/EHa**.

## <a name="see-also"></a>См. также раздел

[Обработка исключений](../extensions/exception-handling-cpp-component-extensions.md)<br/>
[safe_cast](../extensions/safe-cast-cpp-component-extensions.md)<br/>
[Обработка исключений](../cpp/exception-handling-in-visual-cpp.md)
