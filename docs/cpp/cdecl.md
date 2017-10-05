---
title: "__cdecl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __cdecl
- __cdecl_cpp
dev_langs:
- C++
helpviewer_keywords:
- __cdecl keyword [C++]
ms.assetid: 1ff1d03e-fb4e-4562-8be1-74f1ad6427f1
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 5216462ad00d332aec2d00eba78f5d84cdfd7c82
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="cdecl"></a>__cdecl
**Блок, относящийся только к системам Майкрософт**  
  
 По умолчанию для программ на языках C и C++ используется соглашение о вызовах `__cdecl`. Поскольку стек очищается вызывающим объектом, можно сделать **vararg** функции. `__cdecl` Соглашение о вызовах создает исполняемые файлы большего размера, чем [__stdcall](../cpp/stdcall.md), так как он требуется каждый вызов функции содержал код очистки стека. В следующем списке показана реализация этого соглашения о вызовах.  
  
|Элемент|Реализация|  
|-------------|--------------------|  
|Порядок передачи аргументов|Справа налево.|  
|Обязанность по обслуживанию стека|Вызывающая функция выводит аргументы из стека.|  
|Соглашение об оформлении имен|Символ подчеркивания (_) перед именами ставится, за исключением случаев \__cdecl функций, использующих компоновку C экспортируются.|  
|Соглашение о преобразовании регистра|Изменение регистра не выполняется.|  
  
> [!NOTE]
>  Дополнительные сведения см. в разделе [декорированные имена](../build/reference/decorated-names.md).  
  
 Задайте модификатор `__cdecl` перед именем переменной или функции. Поскольку имена и соглашения о вызовах C используются по умолчанию, только один раз необходимо использовать `__cdecl` в x86 код — после указания **/Gv** (vectorcall), **/Gz** (stdcall) или ** / GR** параметр компилятора (fastcall). [/Gd](../build/reference/gd-gr-gv-gz-calling-convention.md) силы параметр компилятора `__cdecl` соглашение о вызовах.  
  
 На процессорах ARM и x64 `__cdecl` принимается, но обычно игнорируется компилятором. По соглашению на ARM и x64 аргументы передаются в регистрах, когда это возможно, а последующие аргументы передаются в стек. В x64 кода, используйте `__cdecl` для переопределения **/Gv** параметр компилятора и использовать соглашение о вызовах по умолчанию x64.  
  
 Если используется внестрочное определение нестатической функции класса, то модификатор соглашения о вызовах не должен быть задан во внестрочном определении. То есть для нестатических методов-членов считается, что соглашение о вызовах, указанное во время объявления, было сделано в точке определения. Рассмотрим следующее определение класса:  
  
```cpp  
struct CMyClass {  
   void __cdecl mymethod();  
};  
```  
  
 В этом случае следующий код:  
  
```cpp  
void CMyClass::mymethod() { return; }  
```  
  
 эквивалентен следующему:  
  
```cpp  
void __cdecl CMyClass::mymethod() { return; }  
```  
  
## <a name="example"></a>Пример  
 В следующем примере компилятору дается инструкция использовать для функции `system` соглашения об именовании и вызовах C:  
  
```cpp  
// Example of the __cdecl keyword on function  
int __cdecl system(const char *);  
// Example of the __cdecl keyword on function pointer  
typedef BOOL (__cdecl *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);  
```  
  
## <a name="see-also"></a>См. также  
 [Передача аргументов и соглашения об именовании](../cpp/argument-passing-and-naming-conventions.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)
