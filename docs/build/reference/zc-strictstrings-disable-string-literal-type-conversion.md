---
title: "-Zc: strictStrings (отключение преобразования типов строковых литералов) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /Zc:strictStrings
- strictStrings
dev_langs: C++
helpviewer_keywords:
- /Zc:strictStrings
- -Zc compiler options (C++)
- strictStrings
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: b7eb3f3b-82c1-48a2-8e63-66bad7397b46
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f316c5fc9209f968219d770a15e6576880b69954
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="zcstrictstrings-disable-string-literal-type-conversion"></a>/Zc:strictStrings (отключение преобразования типов строковых литералов)
Если этот параметр указан, компилятор требует строгого соответствия `const`-квалификации для указателей, инициализированных с помощью строковых литералов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Zc:strictStrings[-]  
```  
  
## <a name="remarks"></a>Примечания  
 Если **/Zc: strictstrings** указан, компилятор принудительно применяет стандартные квалификаторы `const` c++ к строковым литералам, как тип "массив `const char`" или "массив `const wchar_t`", в зависимости от объявления. Строковые литералы являются неизменяемыми, и при попытке изменения содержимого одного из них возникает ошибка нарушения доступа во время выполнения. Необходимо объявить указатель на строку как указатель `const`, чтобы инициализировать его с помощью строкового литерала, или использовать явное приведение `const_cast` для инициализации указателя, не являющегося указателем `const`. По умолчанию или если **/Zc:strictStrings-** указан, компилятор не применяет принудительно стандартные квалификаторы `const` квалификации для указателей на строки, инициализируются с помощью строковых литералов.  
  
 Используйте **/Zc: strictstrings** параметр, чтобы предотвратить компиляцию неверного кода. В этом примере демонстрируется, как простая ошибка объявления приводит к сбою во время выполнения.  
  
```cpp  
// strictStrings_off.cpp  
// compile by using: cl /W4 strictStrings_off.cpp  
int main() {  
   wchar_t* str = L"hello";  
   str[2] = L'a'; // run-time error: access violation  
}  
```  
  
 Когда **/Zc: strictstrings** — включена, и тот же код сообщает об ошибке в объявлении `str`.  
  
```cpp  
// strictStrings_on.cpp  
// compile by using: cl /Zc:strictStrings /W4 strictStrings_on.cpp  
int main() {  
   wchar_t* str = L"hello"; // error: Conversion from string literal   
   // loses const qualifier  
   str[2] = L'a';   
}  
```  
  
 При использовании `auto` для объявления указателя на строку компилятор автоматически создает правильное объявление типа указателя `const`. О попытке изменить содержимое указателя `const` компилятор сообщает как об ошибке.  
  
> [!NOTE]
>  В стандартной библиотеке C++ [!INCLUDE[cpp_dev12_long](../../build/reference/includes/cpp_dev12_long_md.md)] не поддерживает **/Zc: strictstrings** параметра компилятора в отладочных построений. Если присутствует несколько [C2665](../../error-messages/compiler-errors-2/compiler-error-c2665.md) выход ошибок сборки, это может быть причиной.  
  
 Дополнительные сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Выберите **C/C++** папки.  
  
3.  Выберите **командной строки** страницу свойств.  
  
4.  Изменить **Дополнительные параметры** включив `/Zc:strictStrings` и выберите **ОК**.  
  
## <a name="see-also"></a>См. также  
 [/Zc (соответствие)](../../build/reference/zc-conformance.md)