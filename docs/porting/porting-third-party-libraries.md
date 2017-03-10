---
title: "Перенос сторонних библиотек | Документы Майкрософт"
ms.custom: 
ms.date: 01/10/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- 3rd-party libraries
- vspkg
ms.assetid: b055ed20-8a9e-45b2-ac2a-e3d94271c009
caps.latest.revision: 0
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
translationtype: Human Translation
ms.sourcegitcommit: 8630a5c0b97b85e0dc75e8b470974bb7d223a511
ms.openlocfilehash: 1d85010b6068d52d8522875a3c47561ad777d345
ms.lasthandoff: 02/24/2017

---

# <a name="porting-third-party-libraries"></a>Перенос сторонних библиотек

При обновлении проекта до текущей версии Visual C++ также необходимо обновить все библиотеки, которые применяются в проекте, чтобы библиотеки и проект были построены с использованием одной версии и вида компилятора. (Дополнительные сведения см. в статье [Overview of potential upgrade issues](overview-of-potential-upgrade-issues-visual-cpp.md) (Общие сведения, о возможных проблемах, возникающих при обновлении).) 

## <a name="introducing-vcpkg"></a>Знакомство с vcpkg
В прошлом поиск и обновление сторонних библиотек иногда оказывался непростой задачей. В целях упрощения получения и перестроения сторонних библиотек с открытым кодом C++ группа разработчиков Visual C++ создала программу командной строки, которая называется **VC++ Packaging Tool** или **vcpkg**. В Vcpkg есть каталог с возможностью поиска, содержащий множество популярных библиотек с открытым исходным кодом C++. Можно установить любую библиотеку в каталоге непосредственно из командной строки vcpkg. При установке библиотеки Vcpkg создает на компьютере дерево каталогов и добавляет в папку файлы .h, .lib и двоичные файлы. Эту папку можно использовать в командной строке компиляции или интегрировать в Visual Studio 2015 или более позднюю версию с помощью команды vcpkg integrate install. После интеграции файла библиотеки Visual Studio может найти его и добавить в новый созданный проект. Чтобы использовать библиотеку, просто включите ее (#include), и Visual Studio автоматически добавит файл .lib в параметры проекта и скопирует DLL в папку решения.

## <a name="acquisition-and-usage"></a>Получение и использование

Можно скачать vcpkg из [vcpkg репозитория GitHub][vcpkg](https://github.com/Microsoft/vcpkg/).

 - Чтобы найти библиотеку в каталоге: vcpkg search <LibName>
 - Чтобы получить библиотеку (например, Boost): vcpkg install boost
 - Чтобы получить список библиотек, установленных в данный момент: vcpkg list

В записи блога [Vcpkg: средство для получения и сборки библиотек открытым исходным кодом C++ в Windows](https://blogs.msdn.microsoft.com/vcblog/2016/09/19/vcpkg-a-tool-to-acquire-and-build-c-open-source-libraries-on-windows/) объясняются принципы работы vcpkg и приводится список поддерживаемых библиотек. Список обновляется еженедельно.

## <a name="reporting-issues"></a>Сообщение о проблемах
Если библиотека отсутствует в каталоге vcpkg, можно открыть обращение в [репозитории GitHub](https://github.com/Microsoft/vcpkg/issues), где его увидят представители сообщества и группа разработчиков Visual C++, которые затем могут создать файла переноса для этой библиотеки.

Если это проприетарные сторонние библиотеки (не поддерживающие открытый исходный код), рекомендуется обратиться к поставщику библиотек. Однако мы хотим знать все используемые вами библиотеки такого типа. Сообщите нам, какая из них вам нужна (вы можете связаться с нами по адресу vcupgrade@microsoft.com).

  
## <a name="see-also"></a>См. также  
 [Руководство по переносу и обновлению Visual C++](visual-cpp-porting-and-upgrading-guide.md)

