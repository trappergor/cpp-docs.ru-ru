---
title: Сводка времени существования и видимости | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- lifetime, and visibility
- visibility, identifiers
ms.assetid: ea05a253-7658-482c-9a6b-abd71169c42d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6f2c8b6f9c6be0b07dba710e50f71f96bdf3f0eb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="summary-of-lifetime-and-visibility"></a>Сводка времени существования и видимости
В следующей таблице приведена сводка характеристик времени существования и видимости для большинства идентификаторов. В первых трех столбцах приведены атрибуты, определяющие время существования и видимость. Идентификатор с атрибутами, указанными в первых трех столбцах, имеет время существования и видимость, указанные в четвертом и пятом столбцах. Однако таблица охватывает не все возможные случаи. Дополнительные сведения см. в статье о [классах хранения](../c-language/c-storage-classes.md).  
  
### <a name="summary-of-lifetime-and-visibility"></a>Сводка времени существования и видимости  
  
|Атрибуты:<br /><br /> Уровень|Элемент|Спецификатор<br /><br /> класса хранения|Результат: ;<br /><br /> Время существования|Видимость|  
|---------------------------|----------|----------------------------------|--------------------------|----------------|  
|Область видимости файла|Определение переменной|**static**|Global|Оставшаяся часть файла исходного кода, в котором встречается|  
||Объявление переменной|`extern`|Global|Оставшаяся часть файла исходного кода, в котором встречается|  
||Прототип или определение функции|**static**|Global|Один файл исходного кода|  
||Прототип функции|`extern`|Global|Оставшаяся часть файла исходного кода|  
|Область действия блока|Объявление переменной|`extern`|Global|Block|  
||Определение переменной|**static**|Global|Block|  
||Определение переменной|**auto** или **register**|Локальная|Block|  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание:  
 В следующем примере показаны блоки, вложение и видимость переменных:  
  
### <a name="code"></a>Код  
  
```  
// Lifetime_and_Visibility.c  
  
#include <stdio.h>  
  
int i = 1;  // i defined at external level  
  
int main()  // main function defined at external level  
{  
    printf_s( "%d\n", i ); // Prints 1 (value of external level i)  
    {                                 // Begin first nested block  
        int i = 2, j = 3;          // i and j defined at internal level  
        printf_s( "%d %d\n", i, j );  // Prints 2, 3  
        {                             // Begin second nested block  
            int i = 0;                // i is redefined  
            printf_s( "%d %d\n", i, j ); // Prints 0, 3  
        }                             // End of second nested block  
        printf_s( "%d\n", i );        // Prints 2 (outer definition  
                                      //  restored)  
    }                                 // End of first nested block  
    printf_s( "%d\n", i );            // Prints 1 (external level  
                                      // definition restored)  
    return 0;  
}   
```  
  
### <a name="comments"></a>Комментарии  
 В этом примере имеется 4 уровня видимости: внешний уровень и 3 уровня блоков. Значения выводятся на экран, как указано в комментариях после каждого оператора.  
  
## <a name="see-also"></a>См. также  
 [Время жизни, область, видимость и компоновка](../c-language/lifetime-scope-visibility-and-linkage.md)