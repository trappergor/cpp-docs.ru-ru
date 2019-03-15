---
title: Сборки со строгими именами (подписывание сборок) (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- assemblies [C++]
- signing assemblies
- .NET Framework [C++], assembly signing
- assemblies [C++], signing
- linker [C++], assembly signing
- strong-named assemblies [C++]
ms.assetid: c337cd3f-e5dd-4c6f-a1ad-437e85dba1cc
ms.openlocfilehash: ac46d069ece3c75af93f93497169d054b45267d0
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57813933"
---
# <a name="strong-name-assemblies-assembly-signing-ccli"></a>Сборки со строгими именами (подписывание сборок) (C++/CLI)

Здесь описывается, как можно подписать сборку, часто называют присвоении сборке строгого имени.

## <a name="remarks"></a>Примечания

При использовании Visual C++, используйте параметры компоновщика сборки во избежание проблем, связанных с CLR-атрибуты для подписи сборки:

- <xref:System.Reflection.AssemblyDelaySignAttribute>

- <xref:System.Reflection.AssemblyKeyFileAttribute>

- <xref:System.Reflection.AssemblyKeyNameAttribute>

Причины не с помощью атрибутов: тот факт, что имя ключа является видимым в метаданных сборки, которые могут представлять угрозу безопасности, если имя файла содержит конфиденциальную информацию. Кроме того процесс сборки, используемые в среде разработки Visual C++ станут недействительными ключ, с помощью которого подписана сборка, если вы используете атрибуты среды CLR для создания сборки строгим именем и затем запустите средство завершающей обработки, например mt.exe на сборку.

Если построение из командной строки, используйте параметры компоновщика, чтобы подписать сборку и запустите средство завершающей обработки (например, mt.exe), необходимо будет заново подписать сборку с помощью sn.exe. Кроме того можно создать и отложить подпись сборки и после запуска средства завершающей обработки, выполните области действия подписи.

Если вы используете атрибуты подписи при создании в среде разработки, можно успешно подписать сборку путем явного вызова sn.exe ([Sn.exe (средство строгих имен)](/dotnet/framework/tools/sn-exe-strong-name-tool)) в событие после построения. Дополнительные сведения см. в разделе [Задание событий сборки](../build/specifying-build-events.md). Время сборки может быть меньше, если вы используете атрибуты и события после сборки, чем при использовании параметров компоновщика.

Следующие параметры компоновщика поддерживают подписывание сборок:

- [/DELAYSIGN (частичное подписание сборки)](../build/reference/delaysign-partially-sign-an-assembly.md)

- [/KEYFILE (определение ключа или пары ключей для подписи сборки)](../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/KEYCONTAINER (определение контейнера ключей для подписи сборки)](../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)

Дополнительные сведения о строгих сборках см. в разделе [Создание и использование сборок со строгими именами](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies).

## <a name="see-also"></a>См. также

[Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
