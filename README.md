This is a ZF2 Wrapper for Apache Tika.

It allows you to retrieve text, metadata and language from complex
documents.


Supported formats
-----------------

It supports opendocument, office .doc and .docx, pdf, images, videos and
a lot more !

See http://tika.apache.org/1.1/formats.html for details.


Install with composer
------------------------
Add the package dependency `ogogo/tika` in your composer.json 

    {
        "require": {
            "ogogo/tika": "dev-master" 
        }   
    }

Install with composer

    php composer.phar install


Usage
------------------------

In your own project, assuming you have an opendocument test.odt in the
current directory

    <?php
    use Ogogo\Lib\Tika\TikaApp;
     
    $testFile = new \SplFileInfo(__DIR__."/yourdocument.pdf");
    $tikaApp = new TikaApp();
     
    $plaintext = $tikaApp->getText($testFile);
     
    $metadataArray = $tikaApp->getMetaData($testFile);
    
    $language = $tikaApp->getLanguage($testFile);

