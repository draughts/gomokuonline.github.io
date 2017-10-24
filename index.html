<?php
session_save_path(dirname($_SERVER['DOCUMENT_ROOT']) . '/tmp');
session_start();
ob_start();

$base = "https://en.wikipedia.org"; //SET THIS TO THE URL OF THE WEBSITE THAT YOU WANT TO MIRROR

$ckfile       = '/tmp/cookie-' . session_id();
$cookiedomain = str_replace("http://www.", "", $base);
$cookiedomain = str_replace("https://www.", "", $cookiedomain);
$cookiedomain = str_replace("www.", "", $cookiedomain);
$url          = $base . $_SERVER['REQUEST_URI'];
if ($_SERVER['HTTPS'] == 'on') {
    $mydomain = 'https://' . $_SERVER['HTTP_HOST'];
} else {
    $mydomain = 'http://' . $_SERVER['HTTP_HOST'];
}
$curlSession = curl_init();
curl_setopt($curlSession, CURLOPT_URL, $url);
curl_setopt($curlSession, CURLOPT_HEADER, 1);
if ($_SERVER['REQUEST_METHOD'] == 'POST') {
    $postinfo = '';
    foreach ($_POST as $key => $value) {
        $postinfo .= $key . '=' . urlencode($value) . '&';
    }
    rtrim($postinfo, '&');
    curl_setopt($curlSession, CURLOPT_POST, 1);
    curl_setopt($curlSession, CURLOPT_POSTFIELDS, $postinfo);
}
curl_setopt($curlSession, CURLOPT_RETURNTRANSFER, 1);
curl_setopt($curlSession, CURLOPT_TIMEOUT, 30);
curl_setopt($curlSession, CURLOPT_COOKIEJAR, $ckfile);
curl_setopt($curlSession, CURLOPT_COOKIEFILE, $ckfile);
foreach ($_COOKIE as $k => $v) {
    if (is_array($v)) {
        $v = serialize($v);
    }
    curl_setopt($curlSession, CURLOPT_COOKIE, "$k=$v; domain=.$cookiedomain ; path=/");
}
$response = curl_exec($curlSession);
if (curl_error($curlSession)) {
    print curl_error($curlSession);
} else {
    $response  = str_replace("HTTP/1.1 100 Continue\r\n\r\n", "", $response);
    $ar        = explode("\r\n\r\n", $response, 2);
    $header    = $ar[0];
    $body      = $ar[1];
    $header_ar = split(chr(10), $header);
    foreach ($header_ar as $k => $v) {
        if (!preg_match("/^Transfer-Encoding/", $v)) {
            $v = str_replace($base, $mydomain, $v);
            header(trim($v));
        }
    }
    $body = str_replace($base, $mydomain, $body);
    
    //USE THE REPLACE FUNCTION BELOW TO REPLACE CONTENT/CODE OF THE ORIGIN SITE
    // eg. $body = str_replace('Welcome to SiteA','Welcome to SiteB', $body);
    
    $body = str_replace('REPLACE THIS', 'WITH THIS', $body);
    $body = str_replace('REPLACE THIS', 'WITH THIS', $body);
    $body = str_replace('REPLACE THIS', 'WITH THIS', $body);
    print $body;
}
curl_close($curlSession);