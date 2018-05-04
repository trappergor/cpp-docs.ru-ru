---
title: TypeName | Документы Microsoft
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
ms.openlocfilehash: b6eebf038fbe3e5e18e3f2a1e8e7a2aa2554bf41
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="typename"></a>typename
В определениях шаблонов содержит указание компилятору, что Неизвестный идентификатор представляет собой тип. В списках параметров шаблона используется для указания параметра типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
typename identifier;  
```  
  
## <a name="remarks"></a>Примечания  
 Это ключевое слово следует использовать, если имя в определении шаблона — это полное имя, которое зависит от аргумента шаблона; он является необязательным, если полное имя не зависит от. Дополнительные сведения см. в разделе [шаблоны и разрешение имен](../cpp/templates-and-name-resolution.md).  
  
 **TypeName** может использоваться любой тип в любом месте объявления или определения шаблона. В списке базовых классов оно не допускается, если не применяется в качестве аргумента шаблона для базового класса шаблона.  
  
```  
template <class T>  
class C1 : typename T::InnerType // Error - typename not allowed.  
{};  
template <class T>  
class C2 : A<typename T::InnerType>  // typename OK.  
{};  
```  
  
 **Typename** ключевое слово может также использоваться вместо **класса** в списках параметров шаблона. Например следующие инструкции семантически эквивалентны:  
  
```  
template<class T1, class T2>...  
template<typename T1, typename T2>...  
```  
  
## <a name="example"></a>Пример  
  
```  
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