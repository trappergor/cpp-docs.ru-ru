---
title: code_seg | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- code_seg_CPP
- vc-pragma.code_seg
dev_langs:
- C++
helpviewer_keywords:
- pragmas, code_seg
- code_seg pragma
ms.assetid: bf4faac1-a511-46a6-8d9e-456851d97d56
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ae4c8834609552c469eff8ca382a4e14ca077cfd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46428191"
---
# <a name="codeseg"></a>code_seg
Определяет текстовый сегмент, в котором хранятся функции в OBJ-файле.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#pragma code_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
### <a name="paramters"></a>Параметры
  
**push**<br/>
(Необязательно) Помещает запись во внутреннем стеке компилятора. Объект **принудительной** может иметь *идентификатор* и *имя сегмента*.  
  
**pop**<br/>
(Необязательно) Удаление записи из верхней части внутреннего стека компилятора.  
  
*identifier*<br/>
(Необязательно) При использовании с **принудительной**, назначает имя записи во внутреннем стеке компилятора. При использовании с **pop**, извлекает записи из внутреннего стека до *идентификатор* удаляется; Если *идентификатор* не найден во внутреннем стеке не выводятся.  
  
*Идентификатор* позволяет вывести только с одним несколько записей **pop** команды.  
  
"*имя сегмента*"<br/>  
(Необязательно) Имя сегмента. При использовании с **pop**, стек выводится и *имя сегмента* становится активным именем текстового сегмента.  
  
"*класс сегмента*"<br/>
(Необязательно) Игнорируется, но включается для совместимости с версиями C++ до версии 2.0.  
  
## <a name="remarks"></a>Примечания  
 
**Code_seg** директива pragma управляет размещением объектный код, созданный для шаблонов с созданными экземплярами, а также код, созданный неявно с помощью компилятора — например, специальных функций-членов. Мы рекомендуем использовать ["__declspec(code_seg(...))" ](../cpp/code-seg-declspec.md) вместо этого атрибут, поскольку она предоставляет управления размещением всего объектного кода. Сюда включается созданный компилятором код.  
  
Объект *сегмент* в OBJ-файл представляет собой именованный блок данных, который загружается в память как одно целое. Объект *сегмент текста* сегмент, содержащий исполняемый код. В этой статье термины *сегмент* и *разделе* являются взаимозаменяемыми.  
  
**Code_seg** директива pragma указывает компилятору поместить весь последующий объектный код из блока трансляции в сегмент текста с именем *имя сегмента*. По умолчанию для функций в obj-файле используется сегмент с именем .text.  
  
Объект **code_seg** директиву pragma без параметров сбрасывает имя сегмента текста для последующего объектного кода на значение .text.  

Можно использовать [(программа DUMPBIN). EXE](../build/reference/dumpbin-command-line.md) приложение для просмотра OBJ-файлы. Версии DUMPBIN для каждой поддерживаемой целевой архитектуры входят в состав Visual Studio.  
  
## <a name="example"></a>Пример  

В этом примере показано, как использовать **code_seg** директиву pragma, где объектный код помещается элемент управления:  
  
```cpp  
// pragma_directive_code_seg.cpp  
void func1() {                  // stored in .text  
}  
  
#pragma code_seg(".my_data1")  
void func2() {                  // stored in my_data1  
}  
  
#pragma code_seg(push, r1, ".my_data2")  
void func3() {                  // stored in my_data2  
}  
  
#pragma code_seg(pop, r1)      // stored in my_data1  
void func4() {  
}  
  
int main() {  
}  
```  
  
Список имен, которые не должны использоваться для создания раздела, см. в разделе [/SECTION](../build/reference/section-specify-section-attributes.md).  
  
Можно также указать разделы для инициализированных данных ([data_seg](../preprocessor/data-seg.md)), неинициализированных данных ([bss_seg](../preprocessor/bss-seg.md)) и переменных const ([const_seg](../preprocessor/const-seg.md)).  
  
## <a name="see-also"></a>См. также  
 
[code_seg (__declspec)](../cpp/code-seg-declspec.md)<br/>
[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)