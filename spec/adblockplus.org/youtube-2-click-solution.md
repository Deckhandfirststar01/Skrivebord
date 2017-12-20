# Youtube 2-click solution

## Background

If a user visits a site that embeds a youtube video his browser will automatically contact the youtube server to download the neccessary resources to embed the video. With this request many privacy relevant information are transfered to youtube (ip, cookies). Under German law ([§13 TMG](https://www.gesetze-im-internet.de/tmg/__13.html)) the service provider (us) is required to inform the user about the data transfer and to allow him to object the data transfer. This means that simply embedding a youtube video (even via youtube-nocookie.com) is not legal.

This is a solution that enables us to embed youtube videos by first informing the user about the data transfer and asking him to consent before the video is embedded into the website and any information are transfered to youtube ([2-click solution](https://www.datenschutz-notizen.de/eingebettete-youtube-videos-das-muessen-websitebetreiber-datenschutzrechtlich-beachten-1812628/)).


## Embedding the video
	
1. Upon initial page load don't embed the video instead show a preview image as the video placeholder.
    ![](/res/adblockplus.org/youtube-2-click-solution/video-1.png)


2. On hover over the thumbnail image, a dim overlay appears with the play button (aligned central) and the following text (aligned bottom-left): 
    ![](/res/adblockplus.org/youtube-2-click-solution/video-2.png)
    ```
    Click to play this video. Please note that this video is hosted by YouTube. When this video is played, some personal data is transferred to YouTube. For more information, please review YouTube's [privacy policy](https://www.google.com/intl/en/policies/privacy/).
    ```
    1. When JavaScript is disabled the overlay will appear on click.
    1. On touch devices the overlay will appear on click and a native video will load in place of the video thumbnail.
    1. Clicking on the overlay links to the external video, and the video begins to play.
	
    ![](/res/adblockplus.org/youtube-2-click-solution/video-3.png)

    (To prevent users from accidentially skipping the message by double clicking at least 600ms have to pass before a click on the overlay is recognized (The max timeframe for a double click is 500ms).)

## Referencing the 2-click solution

To specify that a youtube video should be embeded using the 2-click solution simply place the preview image at the desired location and fill out abd place the following table next to it (so it's clear to which preview image it's referring to).

`![](/path/to/video/preview-image`

| Item | Details |
| --- | --- | 
| The embed code of the YouTube video | The code after `/embed/` e.g. for `https://www.youtube-nocookie.com/embed/pVYtzF5SemU` it's `pVYtzF5SemU` |
| The thumbnail image | To be provided by author | 
| Thumbnail image alt text | To be provided by author | 
