---
title: "/Zc:referenceBinding (принудительное применение правил привязки ссылку) | Документы Microsoft"
ms.custom: 
ms.date: 12/13/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- referenceBinding
- /Zc:referenceBinding
dev_langs: C++
helpviewer_keywords:
- -Zc compiler options (C++)
- referenceBinding
- Enforce reference binding rules
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 0c6cfaac-9c2a-41a3-aa94-64ca8ef261fc
caps.latest.revision: "1"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0d3d352394b61f95e083a2e6e6f0d888fe210b37
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="zcreferencebinding-enforce-reference-binding-rules"></a>/Zc:referenceBinding (принудительное применение правил привязки ссылка)
Когда **/Zc:referenceBinding** параметр указан, компилятор не допускает ссылку lvalue неконстантной для привязки к временной.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Zc:referenceBinding[-]  
```  
  
## <a name="remarks"></a>Примечания  
Если **/Zc:referenceBinding** указан, компилятор следует разделу 8.5.3 C ++ 11 standard и не позволяет использовать выражения, привязывающие определяемого пользователем типа временных ссылки lvalue неконстантной. По умолчанию или если **/Zc:referenceBinding-** указан, компилятор разрешает таких выражений как расширение Microsoft, но выдается предупреждение уровня 4. Для безопасности кода, переносимость и соответствия, мы рекомендуем использовать **/Zc:referenceBinding**. [/ Разрешительным-](permissive-standards-conformance.md) параметр компилятора неявно устанавливает этот параметр, но его можно переопределить с помощью **/Zc:referenceBinding-**.  
  
## <a name="example"></a>Пример  
  
В этом примере показано расширение Microsoft, которое обеспечивает временное определяемого пользователем типа может быть привязано к ссылку lvalue неконстантной.
```cpp  
// zcreferencebinding.cpp
struct S {
};

void f(S&) {
}

S g() {
    return S{};
}

void main() {
    S& s = g();         // warning C4239 at /W4
    const S& cs = g();  // okay, bound to const ref
    f(g());             // Extension: error C2664 only if /Zc:referenceBinding
}
```  
  
Дополнительные сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Выберите **C/C++** папки.  
  
3.  Выберите **командной строки** страницу свойств.  
  
4.  Изменить **Дополнительные параметры** включив **/Zc:referenceBinding** и выберите **ОК**.  
  
## <a name="see-also"></a>См. также  
[Параметры компилятора](../../build/reference/compiler-options.md)   
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)   
[/Zc (соответствие)](../../build/reference/zc-conformance.md)