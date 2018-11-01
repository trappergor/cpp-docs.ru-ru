---
title: переопределить (C + +/ CLI и C + +/ CX)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- overriding, override keyword [C++]
- override keyword [C++]
ms.assetid: 34d19257-1686-4fcd-96f5-af07c70ba914
ms.openlocfilehash: be7a347e4ddc700acaf4c5a968af648195445485
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50647373"
---
# <a name="override--ccli-and-ccx"></a>переопределить (C + +/ CLI и C + +/ CX)

**Переопределить** контекстно-зависимые ключевое слово указывает, что член типа переопределяет базовый класс или член базового интерфейса.

## <a name="remarks"></a>Примечания

**Переопределить** ключевое слово может использоваться при компиляции для компиляции в машинный код (параметр компилятора по умолчанию), целевые объекты среды выполнения Windows (`/ZW` параметр компилятора), или общие целевые объекты среды выполнения языка (`/clr` параметр компилятора).

Дополнительные сведения об описателях переопределения см. в разделе [спецификатор переопределения](../cpp/override-specifier.md) и [спецификаторы переопределения и компиляции в машинный код](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).

Дополнительные сведения о контекстно-зависимые ключевые слова, см. в разделе [контекстные ключевые слова](../windows/context-sensitive-keywords-cpp-component-extensions.md).

## <a name="examples"></a>Примеры

В следующем примере кода показано, что **переопределить** также может использоваться в компиляциях машинного кода.

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

В следующем примере кода показано, что **переопределить** может использоваться в компиляциях среды выполнения Windows.

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

В следующем примере кода показано, что **переопределить** можно использовать в распространенных компиляций языковой среды выполнения.

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
[Спецификаторы переопределения](../windows/override-specifiers-cpp-component-extensions.md)