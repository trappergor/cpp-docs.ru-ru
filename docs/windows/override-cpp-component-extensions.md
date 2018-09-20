---
title: override (расширения компонентов C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- overriding, override keyword [C++]
- override keyword [C++]
ms.assetid: 34d19257-1686-4fcd-96f5-af07c70ba914
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6071cef3d5669fda86975bb0f27a2b9b87eeb011
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46407274"
---
# <a name="override--c-component-extensions"></a>override (расширения компонентов C++)

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