How To Use Sphinx Directives 
##############################


Embed Content 
*****************

Include Powerpoint From Sharepoint
------------------------------------

Assuming you have a powerpoint document that is hosted on sharepoint, you can 
embed the document as follow:

1. Open the document you want to share on sharepoint
#. Whilst the document is opened, click on ``File`` > ``Share`` > ``Embed this presentation``
#. Copy the iframe code and wrap it around a ``.. raw:: html`` directive

Example 
::
    .. raw:: html 

        <iframe src="https://cummins365.sharepoint.com/sites/GRP_CC51106/_layouts/15/Doc.aspx?sourcedoc={ff2937ac-bbf9-4b09-92cf-ba372837a17b}&amp;action=embedview&amp;
        wdAr=1.7777777777777777" 
        width="876px" height="488px" 
        frameborder="0">This is an embedded 
        <a target="_blank" href="https://office.com">Microsoft Office</a> 
        presentation, powered by <a target="_blank" href="https://office.com/webapps">Office</a>.
        </iframe>

**Will render as**:

.. raw:: html 

    <iframe src="https://cummins365.sharepoint.com/sites/GRP_CC51106/_layouts/15/Doc.aspx?sourcedoc={ff2937ac-bbf9-4b09-92cf-ba372837a17b}&amp;action=embedview&amp;
    wdAr=1.7777777777777777" 
    width="876px" height="488px" 
    frameborder="0">This is an embedded 
    <a target="_blank" href="https://office.com">Microsoft Office</a> 
    presentation, powered by <a target="_blank" href="https://office.com/webapps">Office</a>.
    </iframe>


Excel From sharepoint
----------------------

.. raw:: html

    <iframe width="800" height="600" frameborder="0" scrolling="no" src="https://cummins365.sharepoint.com/sites/GRP_CC51106/_layouts/15/Doc.aspx?sourcedoc={b129c8d3-61d9-4629-ab73-1005a517866e}&action=embedview&wdAllowInteractivity=False&AllowTyping=True&wdHideGridlines=True&wdHideHeaders=True&wdDownloadButton=True&wdInConfigurator=True&wdInConfigurator=True"></iframe>

Youtube Video 
----------------

.. raw:: html

    <iframe width="560" height="315" src="https://www.youtube.com/embed/Dl-BdxNRUqs?si=YPJL7_cHoef7kq52" 
    title="YouTube video player" 
    frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" 
    referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>


References 
*************



