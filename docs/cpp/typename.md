---
title: TypeName | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- typename_cpp
dev_langs:
- C++
helpviewer_keywords:
- typename template specifier
ms.assetid: 52e1d901-220d-4f0d-ab43-dae7e05fb491
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 79ba7d0bda73762d04f0dd11668eb31c275ac03f
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39467932"
---
# <a name="typename"></a>typename
В определениях шаблонов содержит указание компилятору, что Неизвестный идентификатор — это тип. В списках параметров шаблона используется для указания параметра типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typename identifier;  
```  
  
## <a name="remarks"></a>Примечания  
 Необходимо использовать это ключевое слово, если имя в определении шаблона — это полное имя, которое зависит от аргумента шаблона; Это необязательно, если полное имя не зависит от. Дополнительные сведения см. в разделе [шаблоны и разрешение имен](../cpp/templates-and-name-resolution.md).  
  
 **TypeName** может использоваться любой тип, в любом месте объявления или определения шаблона. В списке базовых классов оно не допускается, если не применяется в качестве аргумента шаблона для базового класса шаблона.  
  
```cpp 
template <class T>  
class C1 : typename T::InnerType // Error - typename not allowed.  
{};  
template <class T>  
class C2 : A<typename T::InnerType>  // typename OK.  
{};  
```  
  
 **Typename** слово может также использоваться вместо **класс** в списках параметров шаблона. Например следующие инструкции семантически эквивалентны:  
  
```cpp 
template<class T1, class T2>...  
template<typename T1, typename T2>...  
```  
  
## <a name="example"></a>Пример  
  
```cpp 
// typename.cpp  
template<class T> class X  
{  
   typename T::Y m_y;   // treat Y as a type  
};  
  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Шаблоны](../cpp/templates-cpp.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)