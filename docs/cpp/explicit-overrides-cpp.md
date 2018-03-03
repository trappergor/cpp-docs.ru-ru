---
title: "Явные переопределения (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- virtual functions [C++], explicit overrides
- overriding, functions
- derived classes [C++], virtual functions
- explicit virtual function overrides
- explicit override of virtual function
ms.assetid: ee583234-5cda-4e90-b55e-3f9fbf079ced
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8e2047b15d245c7c4b8e093e23a9ca6c4f16ac44
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="explicit-overrides-c"></a>Явные переопределения (C++)
**Блок, относящийся только к системам Microsoft**  
  
 Если же виртуальная функция объявлена в двух или более [интерфейсы](../cpp/interface.md) и класс, производный от этих интерфейсов, можно явным образом переопределить каждую виртуальную функцию.  
  
 Сведения о явном переопределении в управляемом коде с использованием нового управляемого синтаксиса см. в разделе [явное переопределение](../windows/explicit-overrides-cpp-component-extensions.md).  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано использование явного переопределения:  
  
```  
// deriv_ExplicitOverrides.cpp  
// compile with: /GR  
extern "C" int printf_s(const char *, ...);  
  
__interface IMyInt1 {  
   void mf1();  
   void mf1(int);  
   void mf2();  
   void mf2(int);  
};  
  
__interface IMyInt2 {  
   void mf1();  
   void mf1(int);  
   void mf2();  
   void mf2(int);  
};  
  
class CMyClass : public IMyInt1, public IMyInt2 {  
public:  
   void IMyInt1::mf1() {  
      printf_s("In CMyClass::IMyInt1::mf1()\n");  
   }  
  
   void IMyInt1::mf1(int) {  
      printf_s("In CMyClass::IMyInt1::mf1(int)\n");  
   }  
  
   void IMyInt1::mf2();  
   void IMyInt1::mf2(int);  
  
   void IMyInt2::mf1() {  
      printf_s("In CMyClass::IMyInt2::mf1()\n");  
   }  
  
   void IMyInt2::mf1(int) {  
         printf_s("In CMyClass::IMyInt2::mf1(int)\n");  
   }  
  
   void IMyInt2::mf2();  
   void IMyInt2::mf2(int);  
};  
  
void CMyClass::IMyInt1::mf2() {  
   printf_s("In CMyClass::IMyInt1::mf2()\n");  
}  
  
void CMyClass::IMyInt1::mf2(int) {  
   printf_s("In CMyClass::IMyInt1::mf2(int)\n");  
}  
  
void CMyClass::IMyInt2::mf2() {  
   printf_s("In CMyClass::IMyInt2::mf2()\n");  
}  
  
void CMyClass::IMyInt2::mf2(int) {  
   printf_s("In CMyClass::IMyInt2::mf2(int)\n");  
}  
  
int main() {  
   IMyInt1 *pIMyInt1 = new CMyClass();  
   IMyInt2 *pIMyInt2 = dynamic_cast<IMyInt2 *>(pIMyInt1);  
  
   pIMyInt1->mf1();  
   pIMyInt1->mf1(1);  
   pIMyInt1->mf2();  
   pIMyInt1->mf2(2);  
   pIMyInt2->mf1();  
   pIMyInt2->mf1(3);  
   pIMyInt2->mf2();  
   pIMyInt2->mf2(4);  
  
   // Cast to a CMyClass pointer so that the destructor gets called  
      CMyClass *p = dynamic_cast<CMyClass *>(pIMyInt1);  
      delete p;  
}  
```  
  
```Output  
In CMyClass::IMyInt1::mf1()  
In CMyClass::IMyInt1::mf1(int)  
In CMyClass::IMyInt1::mf2()  
In CMyClass::IMyInt1::mf2(int)  
In CMyClass::IMyInt2::mf1()  
In CMyClass::IMyInt2::mf1(int)  
In CMyClass::IMyInt2::mf2()  
In CMyClass::IMyInt2::mf2(int)  
```  
  
## <a name="see-also"></a>См. также  
 [Наследование](../cpp/inheritance-cpp.md)