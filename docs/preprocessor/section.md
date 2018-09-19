---
title: раздел | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- section_CPP
- vc-pragma.section
dev_langs:
- C++
helpviewer_keywords:
- pragmas, section
- section pragma
ms.assetid: c67215e9-2c4a-4b0f-b691-2414d2e2d96f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ca2582e4c792e0ef60cb11d632c6f4e88891852d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45726054"
---
# <a name="section"></a>section
Создает раздел в OBJ-файле.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#pragma section( "section-name" [, attributes] )  
```  
  
## <a name="remarks"></a>Примечания  
 
Значение условия *сегмент* и *разделе* являются взаимозаменяемыми в этом разделе.  
  
После определения раздел остается допустимым для остальной части компиляции. Тем не менее, необходимо использовать [__declspec(allocate)](../cpp/allocate.md) или не будут помещены в разделе.  
  
*Имя раздела* — это обязательный параметр, который будет использоваться имя раздела. Имя не должно конфликтовать со стандартными именами раздела. См. в разделе [/SECTION](../build/reference/section-specify-section-attributes.md) список имен не следует использовать при создании раздела.  
  
*атрибуты* — необязательный параметр, состоящий из одного или нескольких атрибутов с разделителями запятыми, которые требуется присвоить разделу. Возможные *атрибуты* являются:  

|Атрибут|Описание|
|-|-|
|**read**|Позволяет выполнять операции чтения данных.|
|**write**|Позволяет выполнять операции записи данных.|
|**execute**|Позволяет выполнять код.|
|**Общие**|Предоставляет совместный доступ к разделу всем процессам, загружающим образ.|
|**nopage**|Отмечает раздел как невыгружаемый; используются для драйверов устройств Win32.|
|**NoCache**|Отмечает раздел как некэшируемый; используются для драйверов устройств Win32.|
|**Отменить**|Отмечает раздел как удаляемый; используются для драйверов устройств Win32.|
|**remove**|Отмечает раздел как нерезидентный; драйверы виртуальных устройств (V*x*D) только.|
  
Если не задать атрибуты, раздел будет иметь атрибуты чтения и записи.  
  
## <a name="example"></a>Пример  
 
В следующем примере первая инструкция определяет раздел и его атрибуты. Целое число `j` не помещается в `mysec`, поскольку оно не было объявлено с `__declspec(allocate)`; `j` переходит в раздел данных. Целое число `i` переходит в `mysec` как результат атрибута класса хранения `__declspec(allocate)`.  
  
```cpp  
// pragma_section.cpp  
#pragma section("mysec",read,write)  
int j = 0;  
  
__declspec(allocate("mysec"))  
int i = 0;  
  
int main(){}  
```  
  
## <a name="see-also"></a>См. также  
 
[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)