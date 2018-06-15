---
title: Справочник по XDCMake | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- xdcmake
dev_langs:
- C++
helpviewer_keywords:
- xdcmake program
ms.assetid: 14e65747-d000-4343-854b-8393bf01cbac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 383347dc5cd1ce0dcadff6bdee802b90fd52e85d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33333909"
---
# <a name="xdcmake-reference"></a>Справочник по XDCMake
xdcmake.exe — это программа, которая компилирует XDC-файлы в XML-файл. XDC-файл создается компилятором Visual C++ для каждого файла исходного кода при компиляции исходного кода с параметром [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md), и когда файл исходного кода содержит комментарии документации, помеченные XML-тегами.  
  
### <a name="to-use-xdcmakeexe-in-the-visual-studio-development-environment"></a>Использование xdcmake.exe в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../ide/working-with-project-properties.md).  
  
2.  Откройте папку **Свойства конфигурации**.  
  
3.  Выберите страницу свойств **Комментарии XML-документа**.  
  
> [!NOTE]
>  Параметры xdcmake.exe в командной строке отличаются от параметров, доступных при использовании xdcmake.exe из среды разработки (страницы свойств). Сведения об использовании xdcmake.exe в среде разработки см. в разделе [Страницы свойств средства создания XML-документов](../ide/xml-document-generator-tool-property-pages.md).  
  
## <a name="syntax"></a>Синтаксис  
 xdcmake `input_filename options`  
  
## <a name="parameters"></a>Параметры  
 Здесь:  
  
 `input_filename`  
 Имя для XDC-файлов, используемых в качестве входных для xdcmake.exe. Укажите один или несколько XDC-файлов или значение *.xdc, чтобы использовать все XDC-файлы в текущем каталоге.  
  
 `options`  
 От нуля до нескольких следующих параметров:  
  
|Параметр|Описание:|  
|------------|-----------------|  
|/?, /help|Отображает справку для xdcmake.exe.|  
|/assembly:*имя_файла*|Позволяет задать значение тега \<assembly> в XML-файле.  По умолчанию значение тега \<assembly> совпадает с именем XML-файла.|  
|/nologo|Позволяет запретить вывод сообщения об авторских правах.|  
|/out:*имя_файла*|Позволяет указать имя XML-файла.  По умолчанию именем XML-файла является имя первого XDC-файла, обработанного xdcmake.exe.|  
  
## <a name="remarks"></a>Примечания  
 Visual Studio вызовет xdcmake.exe автоматически при сборке проекта. Кроме того, xdcmake.exe можно вызвать из командной строки.  
  
 Дополнительные сведения о добавлении комментариев документации в файлы исходного кода см. в разделе [Рекомендуемые теги для комментариев документации](../ide/recommended-tags-for-documentation-comments-visual-cpp.md).  
  
## <a name="see-also"></a>См. также  
 [Документация XML](../ide/xml-documentation-visual-cpp.md)