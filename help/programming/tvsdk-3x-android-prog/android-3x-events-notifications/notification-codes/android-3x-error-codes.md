---
title: PSDK Error Codes
description: Information about various error codes, warnings, and native error codes.
---

# PSDK Error Codes {#psdk-error-codes}

Read on to know about PSDK error codes, warnings, and native error codes.

## Errors

The following table provides detailed information about ERROR type notifications. Most errors contain relevant metadata; for example, URL of the resource that failed to download. Some notifications contain metadata to specify whether the problem occurred in the main video content, in the alternate audio content, or in an ad.

<table class="tg">
  <tr>
    <th class="tg-cly1">S.No.</th>
    <th class="tg-cly1">PSDK Error Name</th>
    <th class="tg-cly1">PSDK Error Code</th>
    <th class="tg-0lax">Description</th>
  </tr>
  <tr>
    <td class="tg-cly1">1</td>
    <td class="tg-cly1">SUCCESS</td>
    <td class="tg-cly1">0</td>
    <td class="tg-0lax">Operation performed by underlying API is successful.</td>
  </tr>
  <tr>
    <td class="tg-cly1">2</td>
    <td class="tg-cly1">INVALID_ARGUMENT</td>
    <td class="tg-cly1">1</td>
    <td class="tg-0lax">Data or format of argument provided to underlying API is invalid.</td>
  </tr>
  <tr>
    <td class="tg-cly1">3</td>
    <td class="tg-cly1">NULL_POINTER</td>
    <td class="tg-cly1">2</td>
    <td class="tg-0lax">One of the argument passed in is NULL Or one of the internal members was not initialized.</td>
  </tr>
  <tr>
    <td class="tg-cly1">4</td>
    <td class="tg-cly1">ILLEGAL_STATE</td>
    <td class="tg-cly1">3</td>
    <td class="tg-0lax">The operation is not supported in current player state.</td>
  </tr>
  <tr>
    <td class="tg-cly1">5</td>
    <td class="tg-cly1">INTERFACE_NOT_FOUND</td>
    <td class="tg-cly1">4</td>
    <td class="tg-0lax">The interfaceCast method throws this error when the requested interface is not implemented/inherited by this.</td>
  </tr>
  <tr>
    <td class="tg-cly1">6</td>
    <td class="tg-cly1">CREATION_FAILED</td>
    <td class="tg-cly1">5</td>
    <td class="tg-0lax">Creation of one of the internal resources failed.</td>
  </tr>
  <tr>
    <td class="tg-cly1">7</td>
    <td class="tg-cly1">UNSUPPORTED_OPERATION</td>
    <td class="tg-cly1">6</td>
    <td class="tg-0lax">The requested operation is currently not supported.</td>
  </tr>
  <tr>
    <td class="tg-cly1">8</td>
    <td class="tg-cly1">DATA_NOT_AVAILABLE</td>
    <td class="tg-cly1">7</td>
    <td class="tg-0lax">The requested data is currently not available.</td>
  </tr>
  <tr>
    <td class="tg-cly1">9</td>
    <td class="tg-cly1">SEEK_ERROR</td>
    <td class="tg-cly1">8</td>
    <td class="tg-0lax">An error has occurred while performing a seek operation.</td>
  </tr>
  <tr>
    <td class="tg-cly1">10</td>
    <td class="tg-cly1">UNSUPPORTED_FEATURE</td>
    <td class="tg-cly1">9</td>
    <td class="tg-0lax">This feature/function is not supported.</td>
  </tr>
  <tr>
    <td class="tg-cly1">11</td>
    <td class="tg-cly1">RANGE_ERROR</td>
    <td class="tg-cly1">10</td>
    <td class="tg-0lax">Specified value is out of range.</td>
  </tr>
  <tr>
    <td class="tg-0lax">12</td>
    <td class="tg-0lax">CODEC_NOT_SUPPORTED</td>
    <td class="tg-0lax">11</td>
    <td class="tg-0lax">Given stream's Audio/Video Codec is not supported by TVSDK or by underlying device.</td>
  </tr>
  <tr>
    <td class="tg-0lax">13</td>
    <td class="tg-0lax">MEDIA_ERROR</td>
    <td class="tg-0lax">12</td>
    <td class="tg-0lax">The specified media is not found.</td>
  </tr>
  <tr>
    <td class="tg-0lax">14</td>
    <td class="tg-0lax">NETWORK_ERROR</td>
    <td class="tg-0lax">13</td>
    <td class="tg-0lax">An Error has occurred while downloading a fragment or segment(both video and audio).</td>
  </tr>
  <tr>
    <td class="tg-0lax">15</td>
    <td class="tg-0lax">GENERIC_ERROR</td>
    <td class="tg-0lax">14</td>
    <td class="tg-0lax">Generic error event. Not actually issued by TVSDK. This is only a marker for the end of the range of numerical codes corresponding to TVSDK error events.</td>
  </tr>
  <tr>
    <td class="tg-0lax">16</td>
    <td class="tg-0lax">INVALID_SEEK_TIME</td>
    <td class="tg-0lax">15</td>
    <td class="tg-0lax">The seek time provided is invalid.</td>
  </tr>
  <tr>
    <td class="tg-0lax">17</td>
    <td class="tg-0lax">AUDIO_TRACK_ERROR</td>
    <td class="tg-0lax">16</td>
    <td class="tg-0lax">An error related to an audio track occurred (Alternate Audio)</td>
  </tr>
  <tr>
    <td class="tg-0lax">18</td>
    <td class="tg-0lax">ACCESS_FROM_DIFFERENT_THREAD</td>
    <td class="tg-0lax">17</td>
    <td class="tg-0lax">PSDK API is called from different thread than the thread in which PSDK was initialized.</td>
  </tr>
  <tr>
    <td class="tg-0lax">19</td>
    <td class="tg-0lax">ELEMENT_NOT_FOUND</td>
    <td class="tg-0lax">18</td>
    <td class="tg-0lax">The element is not found.</td>
  </tr>
  <tr>
    <td class="tg-0lax">20</td>
    <td class="tg-0lax">NOT_IMPLEMENTED</td>
    <td class="tg-0lax">19</td>
    <td class="tg-0lax">Feature not implemented.</td>
  </tr>
  <tr>
    <td class="tg-0lax">21</td>
    <td class="tg-0lax">PRE_ROLL_DISABLED</td>
    <td class="tg-0lax">20</td>
    <td class="tg-0lax">The preroll has been disabled via AdvertisingMetadata.</td>
  </tr>
  <tr>
    <td class="tg-0lax">22</td>
    <td class="tg-0lax">PLAYBACK_NOT_AUTHORIZED</td>
    <td class="tg-0lax">57</td>
    <td class="tg-0lax">HLS playback has not been enabled in the Flash Player. See AuthorizedFeatures.enableMediaPlayerHLSPlayback().</td>
  </tr>
  <tr>
    <td class="tg-0lax">23</td>
    <td class="tg-0lax">NETWORK_TIMEOUT</td>
    <td class="tg-0lax">58</td>
    <td class="tg-0lax">Network Timed out while fetching a resource/connecting server.</td>
  </tr>
</table>

## Warnings

The following table provides detailed information about WARN type notifications.
Most warnings contain relevant metadata; for example, the URL of the resource that failed to download. Some notifications contain metadata to specify whether the problem occurred in the main video content, in the alternate audio content, or in an ad.

<table class="tg">
  <tr>
    <th class="tg-cly1">S.No.</th>
    <th class="tg-cly1">Error Name</th>
    <th class="tg-cly1">Code</th>
    <th class="tg-cly1">Description</th>
  </tr>
  <tr>
    <td class="tg-cly1">1</td>
    <td class="tg-cly1">PLAYBACK_OPERATION_FAILED</td>
    <td class="tg-cly1">200</td>
    <td class="tg-cly1">There was an error during playback operation. A playback-related operation has failed</td>
  </tr>
  <tr>
    <td class="tg-cly1">2</td>
    <td class="tg-cly1">NATIVE_WARNING</td>
    <td class="tg-cly1">201</td>
    <td class="tg-cly1">The low-level AVE library issued an error.</td>
  </tr>
  <tr>
    <td class="tg-cly1">3</td>
    <td class="tg-cly1">AD_RESOLVER_FAILED</td>
    <td class="tg-cly1">202</td>
    <td class="tg-cly1">Ad plugin failed to resolve ads.</td>
  </tr>
  <tr>
    <td class="tg-cly1">4</td>
    <td class="tg-cly1">AD_MANIFEST_LOAD_FAILED</td>
    <td class="tg-cly1">203</td>
    <td class="tg-cly1">Failed to load the Ad manifest.</td>
  </tr>
  <tr>
    <td class="tg-cly1">5</td>
    <td class="tg-cly1">AD_RESOLUTION_IN_PROGRESS</td>
    <td class="tg-cly1">204</td>
    <td class="tg-cly1">Operation for Resolving Ads is in progress.</td>
  </tr>
  </table>

## Info

<table class="tg">
  <tr>
    <th class="tg-cly1">S.No.</th>
    <th class="tg-cly1">Error Name</th>
    <th class="tg-cly1">Code</th>
    <th class="tg-cly1">Description</th>
  </tr>
  <tr>
    <td class="tg-cly1">1</td>
    <td class="tg-cly1">REVENUE_OPTIMIZATION_REPORTING</td>
    <td class="tg-cly1">300</td>
    <td class="tg-cly1">TVSDK detailed Notifications for further reporting and analysis.</td>
  </tr>
 </table>

## Native Error Codes

The Video Encoder interface of the AVE returns these video playback notifications in the NATIVE_ERROR metadata object.

<table class="tg">
  <tr>
    <th class="tg-0lax">﻿S.No.</th>
    <th class="tg-0lax">Native Error Name</th>
    <th class="tg-0lax">Native Error Code</th>
    <th class="tg-0lax">Description</th>
  </tr>
  <tr>
    <td class="tg-0lax">1</td>
    <td class="tg-0lax">END_OF_PERIOD</td>
    <td class="tg-0lax">-1</td>
    <td class="tg-0lax">End of period.</td>
  </tr>
  <tr>
    <td class="tg-0lax">2</td>
    <td class="tg-0lax">SUCCESS</td>
    <td class="tg-0lax">0</td>
    <td class="tg-0lax">Operation successful.</td>
  </tr>
  <tr>
    <td class="tg-0lax">3</td>
    <td class="tg-0lax">ASYNC_OPERATION_IN_PROGRESS</td>
    <td class="tg-0lax">1</td>
    <td class="tg-0lax">Asynchronous operation. The operation request has been made. Success/ failure information will be available later.</td>
  </tr>
  <tr>
    <td class="tg-0lax">4</td>
    <td class="tg-0lax">EOF</td>
    <td class="tg-0lax">2</td>
    <td class="tg-0lax">Operation not possible due to end of file (EOF) condition.</td>
  </tr>
  <tr>
    <td class="tg-0lax">5</td>
    <td class="tg-0lax">DECODER_FAILED</td>
    <td class="tg-0lax">3</td>
    <td class="tg-0lax">The decoder failed at runtime.</td>
  </tr>
  <tr>
    <td class="tg-0lax">6</td>
    <td class="tg-0lax">DEVICE_OPEN_ERROR</td>
    <td class="tg-0lax">4</td>
    <td class="tg-0lax">Failed to open hardware decoder.</td>
  </tr>
  <tr>
    <td class="tg-0lax">7</td>
    <td class="tg-0lax">FILE_NOT_FOUND</td>
    <td class="tg-0lax">5</td>
    <td class="tg-0lax">Resource cannot be located.</td>
  </tr>
  <tr>
    <td class="tg-0lax">8</td>
    <td class="tg-0lax">GENERIC_ERROR</td>
    <td class="tg-0lax">6</td>
    <td class="tg-0lax">Generic error.</td>
  </tr>
  <tr>
    <td class="tg-0lax">9</td>
    <td class="tg-0lax">IRRECOVERABLE_ERROR</td>
    <td class="tg-0lax">7</td>
    <td class="tg-0lax">An error condition that the Video Engine cannot recover from.</td>
  </tr>
  <tr>
    <td class="tg-0lax">10</td>
    <td class="tg-0lax">LOST_CONNECTION_RECOVERABLE</td>
    <td class="tg-0lax">8</td>
    <td class="tg-0lax">Network error, trying to recover.</td>
  </tr>
  <tr>
    <td class="tg-0lax">11</td>
    <td class="tg-0lax">NO_FIXED_SIZE</td>
    <td class="tg-0lax">9</td>
    <td class="tg-0lax">The size of the resource cannot be determined.</td>
  </tr>
  <tr>
    <td class="tg-0lax">12</td>
    <td class="tg-0lax">NOT_IMPLEMENTED</td>
    <td class="tg-0lax">10</td>
    <td class="tg-0lax">Feature not implemented.</td>
  </tr>
  <tr>
    <td class="tg-0lax">13</td>
    <td class="tg-0lax">OUT_OF_MEMORY</td>
    <td class="tg-0lax">11</td>
    <td class="tg-0lax">Out of memory.</td>
  </tr>
  <tr>
    <td class="tg-0lax">14</td>
    <td class="tg-0lax">PARSE_ERROR</td>
    <td class="tg-0lax">12</td>
    <td class="tg-0lax">Error while parsing the media file.</td>
  </tr>
  <tr>
    <td class="tg-0lax">15</td>
    <td class="tg-0lax">SIZE_UNKNOWN</td>
    <td class="tg-0lax">13</td>
    <td class="tg-0lax">The resource has a size, but it is unknown.</td>
  </tr>
  <tr>
    <td class="tg-0lax">16</td>
    <td class="tg-0lax">UNDER_FLOW</td>
    <td class="tg-0lax">14</td>
    <td class="tg-0lax">Underflow condition.</td>
  </tr>
  <tr>
    <td class="tg-0lax">17</td>
    <td class="tg-0lax">UNSUPPORTED_CONFIG</td>
    <td class="tg-0lax">15</td>
    <td class="tg-0lax">Configuration is not supported.</td>
  </tr>
  <tr>
    <td class="tg-0lax">18</td>
    <td class="tg-0lax">UNSUPPORTED_OPERATION</td>
    <td class="tg-0lax">16</td>
    <td class="tg-0lax">Operation is not supported.</td>
  </tr>
  <tr>
    <td class="tg-0lax">19</td>
    <td class="tg-0lax">WAITING_FOR_INIT</td>
    <td class="tg-0lax">17</td>
    <td class="tg-0lax">Not yet initialized.</td>
  </tr>
  <tr>
    <td class="tg-0lax">20</td>
    <td class="tg-0lax">INVALID_PARAMETER</td>
    <td class="tg-0lax">18</td>
    <td class="tg-0lax">Invalid parameter.</td>
  </tr>
  <tr>
    <td class="tg-0lax">21</td>
    <td class="tg-0lax">INVALID_OPERATION</td>
    <td class="tg-0lax">19</td>
    <td class="tg-0lax">Operation not permitted.</td>
  </tr>
  <tr>
    <td class="tg-0lax">22</td>
    <td class="tg-0lax">OP_ONLY_ALLOWED_IN_PAUSED_STATE</td>
    <td class="tg-0lax">20</td>
    <td class="tg-0lax">The operation is allowed only while paused.</td>
  </tr>
  <tr>
    <td class="tg-0lax">23</td>
    <td class="tg-0lax">OP_INVALID_WITH_AUDIO_ONLY_FILE</td>
    <td class="tg-0lax">21</td>
    <td class="tg-0lax">Operation cannot be used on audio only files.</td>
  </tr>
  <tr>
    <td class="tg-0lax">24</td>
    <td class="tg-0lax">PREVIOUS_STEP_SEEK_IN_PROGRESS</td>
    <td class="tg-0lax">22</td>
    <td class="tg-0lax">Previous seek operation is still in progress.</td>
  </tr>
  <tr>
    <td class="tg-0lax">25</td>
    <td class="tg-0lax">SOURCE_NOT_SPECIFIED</td>
    <td class="tg-0lax">23</td>
    <td class="tg-0lax">Resource not specified.</td>
  </tr>
  <tr>
    <td class="tg-0lax">26</td>
    <td class="tg-0lax">RANGE_ERROR</td>
    <td class="tg-0lax">24</td>
    <td class="tg-0lax">Specified value is out of range.</td>
  </tr>
  <tr>
    <td class="tg-0lax">27</td>
    <td class="tg-0lax">INVALID_SEEK_TIME</td>
    <td class="tg-0lax">25</td>
    <td class="tg-0lax">Invalid seek time.</td>
  </tr>
  <tr>
    <td class="tg-0lax">28</td>
    <td class="tg-0lax">FILE_STRUCTURE_INVALID</td>
    <td class="tg-0lax">26</td>
    <td class="tg-0lax">The file specified does not conform to the expected syntax.</td>
  </tr>
  <tr>
    <td class="tg-0lax">29</td>
    <td class="tg-0lax">COMPONENT_CREATION_FAILURE</td>
    <td class="tg-0lax">27</td>
    <td class="tg-0lax">An essential component could not be created.</td>
  </tr>
  <tr>
    <td class="tg-0lax">30</td>
    <td class="tg-0lax">DRM_INIT_ERROR</td>
    <td class="tg-0lax">28</td>
    <td class="tg-0lax">Failed to create DRM context.</td>
  </tr>
  <tr>
    <td class="tg-0lax">31</td>
    <td class="tg-0lax">CONTAINER_NOT_SUPPORTED</td>
    <td class="tg-0lax">29</td>
    <td class="tg-0lax">Container type is not supported.</td>
  </tr>
  <tr>
    <td class="tg-0lax">32</td>
    <td class="tg-0lax">SEEK_FAILED</td>
    <td class="tg-0lax">30</td>
    <td class="tg-0lax">Seek failed.</td>
  </tr>
  <tr>
    <td class="tg-0lax">33</td>
    <td class="tg-0lax">CODEC_NOT_SUPPORTED</td>
    <td class="tg-0lax">31</td>
    <td class="tg-0lax">Unsupported codec.</td>
  </tr>
  <tr>
    <td class="tg-0lax">34</td>
    <td class="tg-0lax">NETWORK_UNAVAILABLE</td>
    <td class="tg-0lax">32</td>
    <td class="tg-0lax">Network is not available.</td>
  </tr>
  <tr>
    <td class="tg-0lax">35</td>
    <td class="tg-0lax">NETWORK_ERROR</td>
    <td class="tg-0lax">33</td>
    <td class="tg-0lax">Error getting data from the Network.</td>
  </tr>
  <tr>
    <td class="tg-0lax">36</td>
    <td class="tg-0lax">OVERFLOW</td>
    <td class="tg-0lax">34</td>
    <td class="tg-0lax">Overflow.</td>
  </tr>
  <tr>
    <td class="tg-0lax">37</td>
    <td class="tg-0lax">VIDEO_PROFILE_NOT_SUPPORTED</td>
    <td class="tg-0lax">35</td>
    <td class="tg-0lax">Unsupported video profile.</td>
  </tr>
  <tr>
    <td class="tg-0lax">38</td>
    <td class="tg-0lax">PERIOD_NOT_LOADED</td>
    <td class="tg-0lax">36</td>
    <td class="tg-0lax">An operation was attempted on a HOLD period or a period that has not yet been loaded.</td>
  </tr>
  <tr>
    <td class="tg-0lax">39</td>
    <td class="tg-0lax">INVALID_REPLACE_DURATION</td>
    <td class="tg-0lax">37</td>
    <td class="tg-0lax">The replace duration specified is invalid or extends past the end of the stream.</td>
  </tr>
  <tr>
    <td class="tg-0lax">40</td>
    <td class="tg-0lax">CALLED_FROM_WRONG_THREAD</td>
    <td class="tg-0lax">38</td>
    <td class="tg-0lax">API can't be called from the wrong thread. Mostly, for API elements that should be called from Main thread only.</td>
  </tr>
  <tr>
    <td class="tg-0lax">41</td>
    <td class="tg-0lax">FRAGMENT_READ_ERROR</td>
    <td class="tg-0lax">39</td>
    <td class="tg-0lax">Fragment read error. No failover present. Engine will try to read the next fragment.</td>
  </tr>
  <tr>
    <td class="tg-0lax">42</td>
    <td class="tg-0lax">ABORTED</td>
    <td class="tg-0lax">40</td>
    <td class="tg-0lax">The operation was aborted by an explicit Abort or Destroy call.</td>
  </tr>
  <tr>
    <td class="tg-0lax">43</td>
    <td class="tg-0lax">UNSUPPORTED_HLS_VERSION</td>
    <td class="tg-0lax">41</td>
    <td class="tg-0lax">Cannot play this version of HLS media.</td>
  </tr>
  <tr>
    <td class="tg-0lax">44</td>
    <td class="tg-0lax">CANNOT_FAIL_OVER</td>
    <td class="tg-0lax">42</td>
    <td class="tg-0lax">Cannot fail over.</td>
  </tr>
  <tr>
    <td class="tg-0lax">45</td>
    <td class="tg-0lax">HTTP_TIME_OUT</td>
    <td class="tg-0lax">43</td>
    <td class="tg-0lax">HTTP download has timed out.</td>
  </tr>
  <tr>
    <td class="tg-0lax">46</td>
    <td class="tg-0lax">NETWORK_DOWN</td>
    <td class="tg-0lax">44</td>
    <td class="tg-0lax">The user's network connection is down. Playback could stop any moment and will resume when the connection is available.</td>
  </tr>
  <tr>
    <td class="tg-0lax">47</td>
    <td class="tg-0lax">NO_USABLE_BITRATE_PROFILE</td>
    <td class="tg-0lax">45</td>
    <td class="tg-0lax">No usable bit rate profile found in the stream.</td>
  </tr>
  <tr>
    <td class="tg-0lax">48</td>
    <td class="tg-0lax">BAD_MANIFEST_SIGNATURE</td>
    <td class="tg-0lax">46</td>
    <td class="tg-0lax">The manifest has a bad signature. It failed the manifest signing test.</td>
  </tr>
  <tr>
    <td class="tg-0lax">49</td>
    <td class="tg-0lax">CANNOT_LOAD_PLAYLIST</td>
    <td class="tg-0lax">47</td>
    <td class="tg-0lax">Cannot load a playlist.</td>
  </tr>
  <tr>
    <td class="tg-0lax">50</td>
    <td class="tg-0lax">REPLACEMENT_FAILED</td>
    <td class="tg-0lax">48</td>
    <td class="tg-0lax">Replacement specified in an Insert API could not succeed. This means that the insertion succeeded but replacement did not. Replacement could fail if the manifest to be replaced has been removed from the timeline.</td>
  </tr>
  <tr>
    <td class="tg-0lax">51</td>
    <td class="tg-0lax">SWITCH_TO_ASYMMETRIC_PROFILE</td>
    <td class="tg-0lax">49</td>
    <td class="tg-0lax">DRM is switching to an asymmetric profile. All the profiles are expected to be aligned in duration. If not, this warning will be thrown, and there may be jumps in the playback.</td>
  </tr>
  <tr>
    <td class="tg-0lax">52</td>
    <td class="tg-0lax">LIVE_WINDOW_MOVED_BACKWARD</td>
    <td class="tg-0lax">50</td>
    <td class="tg-0lax">Live window is expected to move forward only. If not, this warning will be thrown, and the window will not be read. Because of that, there may be jumps (or stop / long pause) in the playback.</td>
  </tr>
  <tr>
    <td class="tg-0lax">53</td>
    <td class="tg-0lax">CURRENT_PERIOD_EXPIRED</td>
    <td class="tg-0lax">51</td>
    <td class="tg-0lax">Live window moved beyond the current period.</td>
  </tr>
  <tr>
    <td class="tg-0lax">54</td>
    <td class="tg-0lax">CONTENT_LENGTH_MISMATCH</td>
    <td class="tg-0lax">52</td>
    <td class="tg-0lax">The content-length reported by the HTTP server did not match the actual media size.</td>
  </tr>
  <tr>
    <td class="tg-0lax">55</td>
    <td class="tg-0lax">PERIOD_HOLD</td>
    <td class="tg-0lax">53</td>
    <td class="tg-0lax">The media reader is unable to read further because it has reached the time set by setHoldAt API.</td>
  </tr>
  <tr>
    <td class="tg-0lax">56</td>
    <td class="tg-0lax">LIVE_HOLD</td>
    <td class="tg-0lax">54</td>
    <td class="tg-0lax">The media reader is unable to load segments because it has reached the end of the live window. Segment loading will resume when the server ads new media to the live window. This state is usually reached if:<ul><li>The bufferTime is too high (equal to or higher than the live window duration).</li><li>A combination of one or more of insert/ erase API replaced more media than it added.</li><li>The next period is a live period with a pending media replacement (due to InsertBy API call)</li></ul></td>
  </tr>
  <tr>
    <td class="tg-0lax">57</td>
    <td class="tg-0lax">BAD_MEDIA_INTERLEAVING</td>
    <td class="tg-0lax">55</td>
    <td class="tg-0lax">The audio and video interleaving in the media is not done properly. This is a packaging error. The warning is dispatched when the difference exceeds two seconds.</td>
  </tr>
  <tr>
    <td class="tg-0lax">58</td>
    <td class="tg-0lax">DRM_NOT_AVAILABLE</td>
    <td class="tg-0lax">56</td>
    <td class="tg-0lax"></td>
  </tr>
  <tr>
    <td class="tg-0lax">59</td>
    <td class="tg-0lax">PLAYBACK_NOT_AUTHORIZED</td>
    <td class="tg-0lax">57</td>
    <td class="tg-0lax">HLS playback has not been enabled in the Flash Player. See AuthorizedFeatures.enableHLSPlayback.</td>
  </tr>
  <tr>
    <td class="tg-0lax">60</td>
    <td class="tg-0lax">BAD_MEDIA_SAMPLE_FOUND</td>
    <td class="tg-0lax">58</td>
    <td class="tg-0lax">The decoder received a bad sample that cannot be decoded. This is usually not a fatal error but indicates that there may be glitches in the audio/video. Too many instances of this error indicate a bad encoding or bad file.</td>
  </tr>
  <tr>
    <td class="tg-0lax">61</td>
    <td class="tg-0lax">RANGE_SPANS_READ_HEAD</td>
    <td class="tg-0lax">59</td>
    <td class="tg-0lax">After playback has started, the Insert/Replace range should not contain the read head.</td>
  </tr>
  <tr>
    <td class="tg-0lax">62</td>
    <td class="tg-0lax">POSTROLL_WITH_LIVE_NOT_ALLOWED</td>
    <td class="tg-0lax">60</td>
    <td class="tg-0lax">Post-roll insertions are not allowed on a live media. They are, however, allowed after the server marks the media as complete.</td>
  </tr>
  <tr>
    <td class="tg-0lax">63</td>
    <td class="tg-0lax">INTERNAL_ERROR</td>
    <td class="tg-0lax">61</td>
    <td class="tg-0lax">A very rare issue that should never happen.</td>
  </tr>
  <tr>
    <td class="tg-0lax">64</td>
    <td class="tg-0lax">SPS_PPS_FOUND_OUTSIDE_AVCC</td>
    <td class="tg-0lax">62</td>
    <td class="tg-0lax">The stream does not follow the packaging recommendation of always putting H264 SPS/PPS in an AVCC. Seek / playback issues might be seen.</td>
  </tr>
  <tr>
    <td class="tg-0lax">65</td>
    <td class="tg-0lax">PARTIAL_REPLACEMENT</td>
    <td class="tg-0lax">63</td>
    <td class="tg-0lax">Replacement specified in an Insert API was only partially done. This happens when replaceDuration spans over the timeline duration.</td>
  </tr>
  <tr>
    <td class="tg-0lax">66</td>
    <td class="tg-0lax">RENDITION_M3U8_ERROR</td>
    <td class="tg-0lax">64</td>
    <td class="tg-0lax">Rendition playlist had an error loading. This is only for AVE, not for FlashPlayer.</td>
  </tr>
  <tr>
    <td class="tg-0lax">67</td>
    <td class="tg-0lax">NULL_OPERATION</td>
    <td class="tg-0lax">65</td>
    <td class="tg-0lax">Operation does not do anything.</td>
  </tr>
  <tr>
    <td class="tg-0lax">68</td>
    <td class="tg-0lax">SEGMENT_SKIPPED_ON_FAILURE</td>
    <td class="tg-0lax">66</td>
    <td class="tg-0lax">Segment cannot be played and is skipped on failure.</td>
  </tr>
  <tr>
    <td class="tg-0lax">69</td>
    <td class="tg-0lax">INCOMPATIBLE_RENDER_MODE</td>
    <td class="tg-0lax">67</td>
    <td class="tg-0lax">Incompatible render mode.</td>
  </tr>
  <tr>
    <td class="tg-0lax">70</td>
    <td class="tg-0lax">PROTOCOL_NOT_SUPPORTED</td>
    <td class="tg-0lax">68</td>
    <td class="tg-0lax">The Web protocol used in the URL is not supported.</td>
  </tr>
  <tr>
    <td class="tg-0lax">71</td>
    <td class="tg-0lax">PARSE_ERROR_INCOMPATIBLE_VERSION</td>
    <td class="tg-0lax">69</td>
    <td class="tg-0lax">Error while parsing media file.</td>
  </tr>
  <tr>
    <td class="tg-0lax">72</td>
    <td class="tg-0lax">MANIFEST_FILE_UNEXPECTEDLY_CHANGED</td>
    <td class="tg-0lax">70</td>
    <td class="tg-0lax">Manifest file was changed in an unexpected manner.</td>
  </tr>
  <tr>
    <td class="tg-0lax">73</td>
    <td class="tg-0lax">CANNOT_SPLIT_TIMELINE</td>
    <td class="tg-0lax">71</td>
    <td class="tg-0lax">Cannot perform a split operation on a timeline.</td>
  </tr>
  <tr>
    <td class="tg-0lax">74</td>
    <td class="tg-0lax">CANNOT_ERASE_TIMELINE</td>
    <td class="tg-0lax">72</td>
    <td class="tg-0lax">Cannot perform an erase operation on a timeline.</td>
  </tr>
  <tr>
    <td class="tg-0lax">75</td>
    <td class="tg-0lax">DID_NOT_GET_NEXT_FRAGMENT</td>
    <td class="tg-0lax">73</td>
    <td class="tg-0lax">Did not get the next fragment.</td>
  </tr>
  <tr>
    <td class="tg-0lax">76</td>
    <td class="tg-0lax">NO_TIMELINE</td>
    <td class="tg-0lax">74</td>
    <td class="tg-0lax">No timeline present in an internal data structure.</td>
  </tr>
  <tr>
    <td class="tg-0lax">77</td>
    <td class="tg-0lax">LISTENER_NOT_FOUND</td>
    <td class="tg-0lax">75</td>
    <td class="tg-0lax">No listener found in an internal data structure.</td>
  </tr>
  <tr>
    <td class="tg-0lax">78</td>
    <td class="tg-0lax">AUDIO_START_ERROR</td>
    <td class="tg-0lax">76</td>
    <td class="tg-0lax">Unable to start audio.</td>
  </tr>
  <tr>
    <td class="tg-0lax">79</td>
    <td class="tg-0lax">NO_AUDIO_SINK</td>
    <td class="tg-0lax">77</td>
    <td class="tg-0lax">No audio sink present in an internal data structure.</td>
  </tr>
  <tr>
    <td class="tg-0lax">80</td>
    <td class="tg-0lax">FILE_OPEN_ERROR</td>
    <td class="tg-0lax">78</td>
    <td class="tg-0lax">Unable to open file.</td>
  </tr>
  <tr>
    <td class="tg-0lax">81</td>
    <td class="tg-0lax">FILE_WRITE_ERROR</td>
    <td class="tg-0lax">79</td>
    <td class="tg-0lax">Unable to write to a file.</td>
  </tr>
  <tr>
    <td class="tg-0lax">82</td>
    <td class="tg-0lax">FILE_READ_ERROR</td>
    <td class="tg-0lax">80</td>
    <td class="tg-0lax">Unable to read from a file.</td>
  </tr>
  <tr>
    <td class="tg-0lax">83</td>
    <td class="tg-0lax">ID3PARSE_ERROR</td>
    <td class="tg-0lax">81</td>
    <td class="tg-0lax">There was an error parsing ID3 data.</td>
  </tr>
  <tr>
    <td class="tg-0lax">84</td>
    <td class="tg-0lax">SECURITY_ERROR</td>
    <td class="tg-0lax">82</td>
    <td class="tg-0lax">Loading the content failed because of security restrictions.</td>
  </tr>
  <tr>
    <td class="tg-0lax">85</td>
    <td class="tg-0lax">TIMELINE_TOO_SHORT</td>
    <td class="tg-0lax">83</td>
    <td class="tg-0lax">The timeline duration is too short. If this is a live stream, frequent buffering may happen.</td>
  </tr>
  <tr>
    <td class="tg-0lax">86</td>
    <td class="tg-0lax">AUDIO_ONLY_STREAM_START</td>
    <td class="tg-0lax">84</td>
    <td class="tg-0lax">The stream has been switched to an audio-only stream.</td>
  </tr>
  <tr>
    <td class="tg-0lax">87</td>
    <td class="tg-0lax">AUDIO_ONLY_STREAM_END</td>
    <td class="tg-0lax">85</td>
    <td class="tg-0lax">The stream has been switched from audio-only to a stream with video.</td>
  </tr>
  <tr>
    <td class="tg-0lax">88</td>
    <td class="tg-0lax">KEY_NOT_FOUND</td>
    <td class="tg-0lax">87</td>
    <td class="tg-0lax">Key cannot be found.</td>
  </tr>
  <tr>
    <td class="tg-0lax">89</td>
    <td class="tg-0lax">INVALID_KEY</td>
    <td class="tg-0lax">88</td>
    <td class="tg-0lax">The key is invalid.</td>
  </tr>
  <tr>
    <td class="tg-0lax">90</td>
    <td class="tg-0lax">KEY_SERVER_NOT_FOUND</td>
    <td class="tg-0lax">89</td>
    <td class="tg-0lax">Key server does not return a key.</td>
  </tr>
  <tr>
    <td class="tg-0lax">91</td>
    <td class="tg-0lax">MAIN_MANIFEST_UPDATE_TO_BE_HANDLED</td>
    <td class="tg-0lax">90</td>
    <td class="tg-0lax">Cannot handle main manifest update.</td>
  </tr>
  <tr>
    <td class="tg-0lax">92</td>
    <td class="tg-0lax">UNREPORTED_TIME_DISCONTINUITY_FOUND</td>
    <td class="tg-0lax">91</td>
    <td class="tg-0lax">Unreported time (PTS) discontinuity found.</td>
  </tr>
  <tr>
    <td class="tg-0lax">93</td>
    <td class="tg-0lax">UNMATCHED_AV_DISCONTINUITY_FOUND</td>
    <td class="tg-0lax">92</td>
    <td class="tg-0lax">Unmatched Audio and Video discontinuity found.</td>
  </tr>
  <tr>
    <td class="tg-0lax">94</td>
    <td class="tg-0lax">TRICKPLAY_ENDED_DUE_TO_ERROR</td>
    <td class="tg-0lax">93</td>
    <td class="tg-0lax">There was an error while playing media in trick play mode. Trick play mode is ended and the stream is paused. Call Play() to play the media in normal mode.</td>
  </tr>
  <tr>
    <td class="tg-0lax">95</td>
    <td class="tg-0lax">LIVE_WINDOW_MOVED_AHEAD</td>
    <td class="tg-0lax">95</td>
    <td class="tg-0lax">The player is out of the live window and must seek forward to catch up.</td>
  </tr>
</table>
