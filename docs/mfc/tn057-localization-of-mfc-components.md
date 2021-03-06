---
title: 'TN057: Локализация компонентов MFC'
ms.date: 06/28/2018
helpviewer_keywords:
- components [MFC], localizing
- TN057
- resources [MFC], localization
- localization [MFC], MFC resources
- localization [MFC], MFC components
- MFC DLLs [MFC], localizing
- DLLs [MFC], localizing MFC
- localization [MFC], resources
ms.assetid: 5376d329-bd45-41bd-97f5-3d895a9a0af5
ms.openlocfilehash: 552b925bae00e8bb171c543a6ed16e801186bf89
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65611925"
---
# <a name="tn057-localization-of-mfc-components"></a>TN057: Локализация компонентов MFC

> [!NOTE]
> Следующее техническое примечание не было обновлено, поскольку сначала оно было включено в электронную документацию. В результате некоторые процедуры и разделы могут быть устаревшими или неверными. Для получения последних сведений рекомендуется выполнить поиск интересующей темы в алфавитном указателе документации в Интернете.

Эта заметка описывает некоторые принципы и процедуры, которые можно использовать для локализации компонента, если он управлять приложением или объект OLE или библиотеку DLL, которая использует MFC.

## <a name="overview"></a>Обзор

Существует две проблемы для решения при локализации компонент, который использует MFC. Во-первых, необходимо локализовать собственные ресурсы — строки, диалоговые окна и другие ресурсы, относящиеся к компоненту. Большинство компонентов, созданных с помощью MFC также включить и использовать ряд ресурсов, которые определены в MFC. Необходимо указать также локализованные ресурсы MFC. К счастью несколько языков уже предоставляются классами MFC.

Кроме того компонент должны быть готовы запустить в целевой среде (европейская поддержкой DBCS или среду). В большинстве случаев это зависит от приложения обработки символов, с установленным старшим битом правильно и обработка строк с двухбайтовыми символами. MFC включена по умолчанию обе эти среды таким образом, можно иметь один исполнимый код, который используется на всех платформах с только что различные ресурсы, от сети во время установки.

## <a name="localizing-your-components-resources"></a>Локализация ресурсов компонента

Локализация приложения или библиотеки DLL необходимо привлечь просто заменив ресурсы с ресурсами, которые соответствуют целевым языком. Для ваших собственных ресурсов, это относительно простой: редактирования ресурсов в редакторе ресурсов и выполните сборку своего приложения. Если код написан правильно свидетельствует об нет строки или текст, который требуется локализовать жестко в коде C++ — все локализации можно сделать, просто изменив ресурсы. На самом деле вы можете реализовать компонент, таким образом, чтобы все предоставления локализованные версии даже происходит без сборки исходного кода. Это более сложен, но является определенно стоит этого и механизм, выбранного для MFC. Также возможна локализация приложения путем загрузки файла EXE или DLL в редакторе ресурсов и редактирование ресурсов напрямую. Возможно, однако он требует вводит этих изменений каждый раз при создании новой версии приложения.

Для этого можно избежать, рекомендуется найти все ресурсы в отдельной библиотеке DLL, иногда называют вспомогательной библиотеке DLL. Затем эта библиотека DLL динамически загружается во время выполнения и ресурсы загружаются из библиотеки DLL вместо из главного модуля с вашим кодом. MFC поддерживает такой подход. Рассмотрите возможность приложения MyApp. EXE-ФАЙЛА; он может иметь все ее ресурсы в библиотеку DLL с именем MYRES. БИБЛИОТЕКА DLL. В приложении `InitInstance` он выполнит следующие действия, чтобы загрузить этот DLL-ФАЙЛ и заставить MFC загружать ресурсы из этого расположения:

```cpp
CMyApp::InitInstance()
{
    // one of the first things in the init code
    HINSTANCE hInst = LoadLibrary("myres.dll");

    if (hInst != NULL)
        AfxSetResourceHandle(hInst);

    // other initialization code would follow
    // ...
}
```

После этого для MFC будет загружать ресурсы из библиотеки DLL вместо из myapp.exe. Все ресурсы, тем не менее, должен присутствовать в этой библиотеке DLL; MFC не выполняет поиск экземпляра приложения поиске определенного ресурса. Эта методика применяется одинаково хорошо обычные библиотеки DLL MFC, а также элементы управления OLE. Программа установки скопирует соответствующую версию MYRES. Пользователь предпочитает библиотеки DLL, в зависимости от какой язык ресурса.

Это достаточно просто создать ресурс только библиотеки DLL. Создание проекта библиотеки DLL, добавьте к. Версия-Кандидат на него и добавьте необходимые ресурсы. Если у вас есть существующий проект, который не использует этот способ, можно скопировать ресурсы из этого проекта. После добавления файла ресурсов в проект, все почти готово для построения проекта. Единственное, что необходимо сделать — это набор параметров для включения компоновщик **/NOENTRY**. Это сообщает компоновщику о том, что библиотека DLL не имеет точку входа -, так как у него есть не код, он не имеет точку входа.

> [!NOTE]
> Редактор ресурсов Visual C++ 4.0 и более поздних версий поддерживает несколько языков на. RC-файле. Это можно сделать очень легко управлять локализации в одном проекте. Директивы препроцессора, созданные с помощью редактора ресурсов управляет ресурсы для каждого языка.

## <a name="using-the-provided-mfc-localized-resources"></a>С помощью предоставленного MFC локализованные ресурсы

Любое приложение MFC, при построении повторно использует две вещи из MFC: кода и ресурсов. То есть MFC имеет разные сообщения об ошибках, встроенных диалоговых окон и другие ресурсы, которые используются классами MFC. Чтобы полностью локализовать приложение, необходимо локализовать не только ресурсы приложения, но также ресурсы, которые поступают непосредственно из MFC. MFC предоставляет ряд различных языковых файлов ресурсов автоматически, таким образом, если язык, который вы используете один из языков, которые уже поддерживает MFC, необходимо просто убедитесь, что использование локализованных ресурсов.

На момент написания этой статьи MFC поддерживает китайский, немецкий, испанский, французский, итальянский, японский и корейский. Файлы, содержащие эти локализованные версии находятся в MFC\INCLUDE\L.* («L» означает локализованную) каталоги. Немецкий файлы находятся в MFC\INCLUDE\L.DEU, например. Чтобы вызвать приложение для использования вместо файлов, расположенных в MFC\INCLUDE RC-файлов, добавьте `/IC:\PROGRAM FILES\MICROSOFT VISUAL STUDIO .NET 2003\VC7\MFC\INCLUDE\L.DEU` для вашей версии-КАНДИДАТА командной строки (это всего лишь примером; необходимо заменить язык выбора, а также каталог, в котором установлена Visual C ++).

Выше инструкциям будет работать, если приложение статически связано с MFC. Большинство приложений связать динамически (поскольку, по умолчанию мастером приложений). В этом случае является не только код, динамически связанной - то все ресурсы. Таким образом вы можете локализовать ресурсы в приложении, но реализация ресурсы MFC будет загружен из MFC7x.DLL (или более поздней версии) или MFC7xLOC.DLL если он существует. Это можно использовать с двух разных углов.

Более сложный подход — корабле, один из локализованного MFC7xLOC.DLLs (например, MFC7xDEU для немецкого языка, MFC7xESP.DLL испанский т. д.) или более поздней версии и установить соответствующие MFC7xLOC.DLL в системный каталог, когда пользователь устанавливает приложение. Это могут быть очень сложными для разработчика и конечного пользователя и таким образом не рекомендуется. См. в разделе [технические 56 Примечание](../mfc/tn056-installation-of-localized-mfc-components.md) Дополнительные сведения на этой методики и особенностей.

Самый простой и безопасный вариант – включить локализованные ресурсы MFC в приложении или DLL, сам (или его вспомогательной библиотеке DLL, если вы используете). Это позволяет избежать проблемы установки MFC7xLOC.DLL должным образом. Для этого выполните те же инструкции, в случае статического, указанному выше (установка версии-КАНДИДАТА командной строки указывает локализованные ресурсы), за исключением, что необходимо также удалить `/D_AFXDLL` определить, был добавлен с мастером приложений. Когда `/D_AFXDLL` имеет определенные AFXRES. H (и другие файлы MFC версия-Кандидат) не определяют фактически все ресурсы (так как они будут взяты из библиотеки DLL MFC вместо этого).

## <a name="see-also"></a>См. также

[Технические примечания по номеру](../mfc/technical-notes-by-number.md)<br/>
[Технические примечания по категории](../mfc/technical-notes-by-category.md)
