---
title: code_seg | Документы Microsoft
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
ms.openlocfilehash: f958d1652f82f297ae530c1e24bdf331976e0dc0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="codeseg"></a>code_seg
Определяет текстовый сегмент, в котором хранятся функции в OBJ-файле.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#pragma code_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## <a name="remarks"></a>Примечания  
 Директива pragma `code_seg` не управляет размещением ни объектного кода, созданного для шаблонов с созданными экземплярами, ни неявно созданного компилятором кода, например, специальных функций-членов. Мы рекомендуем использовать ["__declspec(code_seg(...))" ](../cpp/code-seg-declspec.md) вместо атрибута, поскольку он предоставляет возможность управления размещением всего объектного кода. Сюда включается созданный компилятором код.  
  
 Объект *сегмент* в OBJ-файл представляет собой именованный блок данных, который загружается в память как одно целое. Объект *сегмент текста* — сегмент, содержащий исполняемый код. В этой статье термины *сегмент* и *раздел* взаимозаменяемы.  
  
 Директива pragma `code_seg` заставляет компилятор поместить весь последующий объектный код из блока трансляции в сегмент текста с именем `segment-name`. По умолчанию для функций в obj-файле используется сегмент с именем .text.  
  
 Директива pragma `code_seg` без параметров сбрасывает имя сегмента текста для последующего объектного кода на значение .text.  
  
 **Принудительная** (необязательно)  
 Помещает запись во внутренний стек компилятора. Объект **принудительной** может иметь `identifier` и `segment-name`.  
  
 **POP** (необязательно)  
 Удаляет запись из вершины внутреннего стека компилятора.  
  
 `identifier` (необязательно)  
 При использовании с **принудительной**, присваивает имя записи во внутреннем стеке компилятора. При использовании с **pop**, извлекает записи из внутреннего стека до `identifier` удаляется; Если `identifier` не найден во внутреннем стеке, ничего не извлекается.  
  
 `identifier` позволяет нескольким записям извлекаться только с одним **pop** команды.  
  
 "`segment-name`" (необязательно)  
 Имя сегмента. При использовании с **pop**, стек выводится и `segment-name` становится активным именем текстового сегмента.  
  
 "`segment-class`" (необязательно)  
 Игнорируется, но включается для обеспечения совместимости с версиями C++ до версии 2.0.  
  
 Можно использовать [DUMPBIN. EXE](../build/reference/dumpbin-command-line.md) приложение для просмотра OBJ-файлы. Версии DUMPBIN для каждой поддерживаемой целевой архитектуры входят в состав [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
## <a name="example"></a>Пример  
 В этом примере показано, как использовать директиву pragma `code_seg` для определения места размещения объектного кода:  
  
```  
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
  
 Список имен, которые не должны использоваться для создания раздела см. в разделе [/SECTION](../build/reference/section-specify-section-attributes.md).  
  
 Можно также указать разделы для инициализированных данных ([data_seg](../preprocessor/data-seg.md)), неинициализированных данных ([bss_seg](../preprocessor/bss-seg.md)) и переменных const ([const_seg](../preprocessor/const-seg.md)).  
  
## <a name="see-also"></a>См. также  
 [code_seg (__declspec)](../cpp/code-seg-declspec.md)   
 [Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)