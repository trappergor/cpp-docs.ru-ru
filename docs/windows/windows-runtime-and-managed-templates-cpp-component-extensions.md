---
title: "Среда выполнения Windows и управляемые шаблоны (расширения компонентов C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "шаблоны, с типами CLR"
ms.assetid: cf59d16b-5514-448b-9a95-e0b4fcb616a6
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Среда выполнения Windows и управляемые шаблоны (расширения компонентов C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Шаблоны позволяют определять прототип среды выполнения Windows или типа среды CLR, а затем создавать варианты этого типа с помощью параметров типа другого шаблона.  
  
## Все среды выполнения  
 Можно создавать шаблоны из значения или ссылочных типов.  Дополнительные сведения о создании типов значения и ссылочных типов см. в разделе [Классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md).  
  
 Дополнительные сведения о стандартных шаблонах классов C\+\+ см. в разделе [Шаблоны классов](../Topic/Class%20Templates.md).  
  
## среда выполнения Windows  
 \(Отсутствуют комментарии для этой функции языка, которая применяется только в среде выполнения Windows\).  
  
### Требования  
 Параметр компилятора: **\/ZW**  
  
## Среда CLR  
 Существуют некоторые ограничения на создание шаблонов класса из управляемых типов, которые показаны в следующих примерах кода.  
  
### Требования  
 Параметр компилятора: **\/clr**  
  
### Примеры  
 **Пример**  
  
 Можно создать универсальный тип с помощью параметра шаблона управляемого типа, но нельзя создать управляемый шаблон с помощью параметра шаблона универсального типа.  Это происходит потому, что универсальные типы разрешаются во время выполнения.  Для получения дополнительной информации см. [Универсальные типы и шаблоны \(Visual C\+\+\)](../windows/generics-and-templates-visual-cpp.md).  
  
```cpp  
// managed_templates.cpp  
// compile with: /clr /c  
  
generic<class T>   
ref class R;   
  
template<class T>   
ref class Z {  
   // Instantiate a generic with a template parameter.  
   R<T>^ r;    // OK  
};  
  
generic<class T>   
ref class R {  
   // Cannot instantiate a template with a generic parameter.  
   Z<T>^ z;   // C3231  
};  
```  
  
 **Пример**  
  
 Универсальный тип или функция не может быть вложена в управляемый шаблон.  
  
```cpp  
// managed_templates_2.cpp  
// compile with: /clr /c  
  
template<class T> public ref class R {  
   generic<class T> ref class W {};   // C2959  
};  
```  
  
 **Пример**  
  
 Нельзя получить доступ к шаблонам, определенным в связанной сборке с помощью синтаксиса языка C\+\+\/CLI, но можно использовать отражение.  Если шаблон не создается \- он не выпускается в метаданные.  При создании экземпляра шаблона только связанные функции\-члены отображаются в метаданных.  
  
```cpp  
// managed_templates_3.cpp  
// compile with: /clr  
  
// Will not appear in metadata.  
template<class T> public ref class A {};  
  
// Will appear in metadata as a specialized type.  
template<class T> public ref class R {  
public:  
   // Test is referenced, will appear in metadata  
   void Test() {}  
  
   // Test2 is not referenced, will not appear in metadata  
   void Test2() {}  
};  
  
// Will appear in metadata.  
generic<class T> public ref class G { };  
  
public ref class S { };  
  
int main() {  
   R<int>^ r = gcnew R<int>;  
   r->Test();  
}  
```  
  
 **Пример**  
  
 Можно изменить управляемый модификатор класса в частичной специализации или явной специализации шаблона класса.  
  
```cpp  
// managed_templates_4.cpp  
// compile with: /clr /c  
  
// class template  
// ref class  
template <class T>  
ref class A {};  
  
// partial template specialization  
// value type  
template <class T>  
value class A <T *> {};  
  
// partial template specialization  
// interface  
template <class T>   
interface class A<T%> {};  
  
// explicit template specialization  
// native class  
template <>  
class A <int> {};  
  
```  
  
## См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)