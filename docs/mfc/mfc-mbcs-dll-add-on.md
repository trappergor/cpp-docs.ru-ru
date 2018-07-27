---
title: Надстройка DLL MFC MBCS | Документация Майкрософт
ms.custom: ''
ms.date: 1/04/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MBCS
- MFC
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aa6840fe54478b88e201dd09950917b95c7a1cc4
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2018
ms.locfileid: "39025738"
---
# <a name="mfc-mbcs-dll-add-on"></a>Надстройка DLL MBCS MFC

Поддержка MFC и его библиотек многобайтовой кодировки (MBCS) требуется дополнительный этап во время установки Visual Studio в Visual Studio 2013, 2015 и 2017.

**Visual Studio 2013**: по умолчанию, библиотеки MFC, установленные в Visual Studio 2013 поддерживают только Юникод разработки. Требуется библиотек MBCS для построения проекта MFC в Visual Studio 2013 с **кодировка** свойство значение **использовать многобайтовую кодировку** или **не задано**. Загрузить библиотеку DLL в [многобайтовая библиотека MFC для Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40770).

**Visual Studio 2015**: Юникод, так и библиотеки MFC MBCS, включаются в состав компонентов установки Visual C++, но поддержка MFC не устанавливается по умолчанию. Visual C++ и MFC относятся к необязательным компонентам в программе установки Visual Studio. Чтобы убедиться в том, что компонент MFC установлен, в программе установки установите переключатель **Выборочная** и в разделе **Языки программирования**убедитесь, что выбраны пункты **Visual C++** и **Microsoft Foundation Classes для C++** . Если вы уже установили Visual Studio, при попытке создания проекта MFC вам будет предложено установить Visual C++ и (или) MFC.

**Visual Studio 2017**: Юникода и многобайтовой Кодировки MFC DLL устанавливаются вместе с **разработка классических приложений C++** рабочей нагрузки, при выборе **MFC и ATL поддерживает** из **необязательно. Компоненты** области. Если установку не включает эти компоненты, перейдите к **файл | Новые проекты** окна и нажмите кнопку **открыть установщик Visual Studio** ссылку.

## <a name="see-also"></a>См. также

[Версии библиотек MFC](../mfc/mfc-library-versions.md)

