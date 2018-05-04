---
title: -EXPORT (экспортирует функцию) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.ExportFunctions
- /export
dev_langs:
- C++
helpviewer_keywords:
- /EXPORT linker option
- EXPORT linker option
- -EXPORT linker option
ms.assetid: 0920fb44-a472-4091-a8e6-73051f494ca0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f366b40e8e40e62f67ec45f3e59ad61eb338c427
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="export-exports-a-function"></a>/EXPORT (экспортирует функцию)
```  
/EXPORT:entryname[,@ordinal[,NONAME]][,DATA]  
```  
  
## <a name="remarks"></a>Примечания  
 В этом случае функцию можно экспортировать из программы, чтобы другие программы можно вызвать функцию. Можно также экспортировать данные. Экспорт обычно определяется в библиотеке DLL.  
  
 *Имя* является имя элемента данных или функции, как он будет использоваться вызывающей программой. `ordinal` Задает индекс в таблице экспорта в диапазоне от 1 до 65 535; Если вы не укажете `ordinal`, будет назначен командой LINK. **NONAME** ключевое слово экспортирует функцию только по порядковому номеру, без *имя*.  
  
 **Данные** ключевое слово указывает, что экспортированный элемент является элементом данных. Элемент данных в клиентской программе должен быть объявлен с помощью **extern __declspec(dllimport)**.  
  
 Существуют три способа экспорта определения, перечислены в рекомендуемом порядке использования:  
  
1.  [__declspec(dllexport)](../../cpp/dllexport-dllimport.md) в исходном коде  
  
2.  [ЭКСПОРТОВ](../../build/reference/exports.md) инструкции в DEF-файла  
  
3.  Спецификации/Export в команде LINK  
  
 Все три метода можно использовать в одной программе. Когда программа LINK создает программу, содержащую экспорты, она также создает библиотеку импорта, если только не используется файл EXP в сборке.  
  
 LINK использует декорированную форму идентификаторов. Компилятор декорирует идентификатор при создании OBJ-файле. Если *имя* указан компоновщику в его недекорированной форме (как оно отображается в исходном коде), LINK пытается найти совпадающее имя. Если не удается найти уникальное соответствие, LINK выдает сообщение об ошибке. Используйте [DUMPBIN](../../build/reference/dumpbin-reference.md) , которая позволяет получить [декорированные имена](../../build/reference/decorated-names.md) форма идентификатора при необходимости укажите его в компоновщик.  
  
> [!NOTE]
>  Не указывайте декорированную форму идентификаторов C, объявляются `__cdecl` или `__stdcall`.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Выберите страницу свойств **Командная строка** .  
  
4.  Введите параметр в **Дополнительные параметры** поле.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)