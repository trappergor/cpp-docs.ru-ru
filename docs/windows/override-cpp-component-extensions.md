---
title: переопределения (расширения компонентов C++) | Документы Microsoft
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
ms.openlocfilehash: 6818256aafc64702e5423a5560c251e6d46750fa
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878883"
---
# <a name="override--c-component-extensions"></a>override (расширения компонентов C++)
Контекстно-зависимое ключевое слово `override` указывает, что член типа переопределяет член базового класса или базового интерфейса.  
  
## <a name="remarks"></a>Примечания  
 `override` Ключевое слово является допустимым при компиляции для компиляции в машинный код (параметр компилятора по умолчанию), целевые объекты среды выполнения Windows (**/ZW** параметр компилятора), или общие объекты среды выполнения языка (**/CLR** компилятора параметр).  
  
 Дополнительные сведения об описателях переопределения см. в разделе [спецификатор переопределения](../cpp/override-specifier.md) и [спецификаторы переопределения и компиляция в машинный код](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).  
  
 Дополнительные сведения о контекстно-зависимые ключевые слова см. в разделе [контекстно-зависимые ключевые слова](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
## <a name="examples"></a>Примеры  
 **Пример**  
  
 В следующем примере кода показано, что `override` также может использоваться в компиляциях машинного кода.  
  
```cpp#  
// override_keyword_1.cpp  
// compile with: /c  
struct I1 {  
   virtual void f();  
};  
  
struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
 **Пример**  
  
 В следующем примере кода показано, что `override` может использоваться в компиляциях среды выполнения Windows.  
  
```cpp#  
// override_keyword_2.cpp  
// compile with: /ZW /c  
ref struct I1 {  
   virtual void f();  
};  
  
ref struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
 **Требования**  
  
 Параметр компилятора: **/ZW**  
  
 **Пример**  
  
 В следующем примере кода показано, что `override` можно использовать в общих компиляций среды выполнения языка.  
  
```cpp#  
// override_keyword_3.cpp  
// compile with: /clr /c  
ref struct I1 {  
   virtual void f();  
};  
  
ref struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
 **Требования**  
  
 Параметр компилятора: **/clr**  
  
## <a name="see-also"></a>См. также  
 [Спецификатор переопределения](../cpp/override-specifier.md)   
 [Спецификаторы переопределения](../windows/override-specifiers-cpp-component-extensions.md)