---
title: override (C++/CLI и C++/CX)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- overriding, override keyword [C++]
- override keyword [C++]
ms.assetid: 34d19257-1686-4fcd-96f5-af07c70ba914
ms.openlocfilehash: 8dc7a0a0e6cf759d956fd701d033bd773e572af3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "65515659"
---
# <a name="override--ccli-and-ccx"></a>override (C++/CLI и C++/CX)

Контекстно-зависимое ключевое слово **override** указывает, что член типа переопределяет член базового класса или базового интерфейса.

## <a name="remarks"></a>Примечания

Ключевое слово **override** обрабатывается при компиляции в машинный код (параметр компилятора по умолчанию), объекты среды выполнения Windows (параметр компиляции `/ZW`) или объекты среды CLR (параметр компилятора `/clr`).

Подробные сведения об описателях переопределения см. в статье [override Specifier](../cpp/override-specifier.md) (Описатель override) и [Override Specifiers and Native Compilations](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md) (Описатели переопределения и компиляции в машинный код).

Подробные сведения о контекстно-зависимых ключевых словах см. в статье [Context-Sensitive Keywords (C++/CLI and C++/CX)](context-sensitive-keywords-cpp-component-extensions.md) (Контекстно-зависимые ключевые слова (C++/CLI and C++/CX)).

## <a name="examples"></a>Примеры

В следующем примере кода показано, как **override** также можно использовать в компиляциях в машинный код.

```cpp
// override_keyword_1.cpp
// compile with: /c
struct I1 {
   virtual void f();
};

struct X : public I1 {
   virtual void f() override {}
};
```

### <a name="example"></a>Пример

В следующем примере кода показано, как **override** также можно использовать в компиляциях в объекты среды выполнения Windows.

```cpp
// override_keyword_2.cpp
// compile with: /ZW /c
ref struct I1 {
   virtual void f();
};

ref struct X : public I1 {
   virtual void f() override {}
};
```

#### <a name="requirements"></a>Требования

Параметр компилятора: `/ZW`

### <a name="example"></a>Пример

В следующем примере кода показано, как **override** также можно использовать в компиляциях в объекты среды CLR.

```cpp
// override_keyword_3.cpp
// compile with: /clr /c
ref struct I1 {
   virtual void f();
};

ref struct X : public I1 {
   virtual void f() override {}
};
```

#### <a name="requirements"></a>Требования

Параметр компилятора: `/clr`

## <a name="see-also"></a>См. также

[Описатель override](../cpp/override-specifier.md)<br/>
[Спецификаторы переопределения](override-specifiers-cpp-component-extensions.md)