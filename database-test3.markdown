---
layout: home
title: Database3
permalink: /database3/
order: 5
---

<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        * {
          box-sizing: border-box;
        }

        .turkish-letters{
          margin:auto;
        }
        .button-default{
          height: 30px;
          width: 30px;
          border: white;
          border-radius: 8px;
          margin: 3px;
          float: left;
          margin-bottom: 30px;
        }
        label.label-checkbox {
          cursor: pointer;
        }

        label.label-checkbox input {
          position: absolute;
          top: 0;
          left: 0;
          visibility: hidden;
          pointer-events: none;
        }

        label.label-checkbox span {
          padding: 11px 21px;
          border: 1px solid #ccc;
          display: inline-block;
          color: #202020;
          border-radius: 6px;
          margin: 4px;
          background: #f5f5f5;
          user-select: none;
        }

        /*for the two buttons so they don't filter */
        label.label-checkbox-reset input {
          position: absolute;
          top: 0;
          left: 0;
          visibility: hidden;
          pointer-events: none;
        }

        label.label-checkbox-reset span {
          padding: 11px 21px;
          border: 1px solid #ccc;
          display: inline-block;
          color: #202020;
          border-radius: 6px;
          margin: 4px;
          background: #f5f5f5;
          user-select: none;
        }

        label.label-checkbox input:checked + span {
          box-shadow: inset 1px 2px 5px #777;
          transform: translateY(1px);
          background: #e5e5e5;
        }

        h1, .dataTable-wrapper {
          max-width: -webkit-calc(800px - (30px * 2));
          max-width: calc(800px - (30px * 2));
          margin-right: auto;
          margin-left: 0px;
          padding-right: 30px;
          padding-left: 30px;
          float: left;
          display: flex;
        }

        .sidebar {
          left: 0;
          width: 20%;
          height: auto;
          padding: 0 0;
          float: left;
        }

        .dataTable-wrapper{
          float: left;
        }

        h2{
          text-align: left;
        }

        .clearfix::after{
          content: "";
          clear: both;
          display: table;
        }


    </style>
    <link rel="stylesheet" href="https://cdn.datatables.net/1.10.11/css/jquery.dataTables.min.css">
  </head>

  <body>
    <p id="test"></p>
    <p id="test2"></p>

   <!--These go near search bar -->
    <div class="category-filter">
      <select id="categoryFilter" class="form-control">
        <option value='-1'>Show All</option>
        <option value='2'>Author Name (Transliteration)</option>
        <option value='6'>Title of Work (Transliteration)</option>
        <option value='11'>Location of Work</option>
        <option value='12'>Publisher</option>
        <option value='18'>Content Location</option>
      </select>
    </div>

    <div id="resets">
      <label class="label-checkbox-reset" id="reset-filter">
        <input type="checkbox">
        <span>Reset Filter</span>
      </label>
      <label class="label-checkbox-reset" id="reset-search">
        <input type="checkbox">
        <span>Reset Search</span>
      </label>
    </div>

    <div id="turkish-letters">
    </div>


    <div class="clearfix">
    <div class="sidebar" id="sidebar">
      <h1>Filter By:</h1>
        <div id="filter-type" class="filter-stuff">
          <h2>Type:</h2>
        </div>
        <div id="lang">
          <h2>Language:</h2>
        </div>
        <div id="script">
          <h2>Script:</h2>
        </div>

        <div id="filter-genres">
          <h2>Genre:</h2>
          <label id="dropdown">Genre -- Choose a language:</label>
          <select name="genres" id="genres">
            <option value="ottoman">Ottoman</option>
            <option value="arabic">Arabic</option>
            <option value="modern-turkish">Modern Turkish</option>
            <option value="english">English</option>
            <option value="french">French</option>
          </select>
        </div>

        <div id="genre-menu-here">
        </div>

    </div> <!--sidebar -->

      <div class="dataTable-wrapper dataTable-loading no-footer sortable searchable fixed-columns" >

      <div class="dataTable-top">

      <div class="dataTable-container">
        <table id="myTable" class="dataTable-table">
          <thead>
            <tr class="headerfooter" style="text-align: right;">
              <th>AUTHOR ID</th>
              <th>AUTHOR NAME (ORIGINAL LANGUAGE)</th>
              <th>AUTHOR NAME TRANSLITERATION</th>
              <th>TITLE ID</th>
              <th>TITLE ID.1</th>
              <th>TITLE OF WORK (ORIGINAL LANGUAGE)</th>
              <th>TITLE OF WORK TRANSLITERATION</th>
              <th>LANGUAGE</th>
              <th>GENRE</th>
              <th>TYPE</th>
              <th>DATE</th>
              <th>MANUSCRIPT CURRENT LOCATION / PRINT ORIGINAL LOCATION</th>
              <th>PUBLISHER</th>
              <th>SCRIPT</th>
              <th>PAGE COUNT</th>
              <th>DIMENSIONS</th>
              <th>ADDITIONAL INFO</th>
              <th>SPECIFIC EDITION BIBLIOGRAPHY</th>
              <th>CONTENT LOCATION</th>
              <th>GENERAL BIBLIOGRAPHY</th>
              <th>NOTES</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <th>1</th>
              <td>علي بن عبد الرحمان</td>
              <td>ʿAlī b. ʿAbd al-Raḥmān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>ترجمهء عجائب المخلوقات</td>
              <td>Terceme-i ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>Terceme; ‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>1099 AH</td>
              <td>İstanbul Üniversitesi, TY, nr. 524</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>174 yaprak</td>
              <td>22x15(6x13) cm</td>
              <td>15 str.</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>Fr. Taechner, "Osmanlılar'da Coğrafya", TM, II, İstanbul, 1926, s.275; •\r\nAdıvar, Osmanlı Türkleri'nde İlim, s.29; G. Kut, s.184-185; aynı müellif, "'Aca'ib alMahlükat", DİA, I, 316; Kemal Özdemir, Osmanli Deniz Haritaları Ali Macar Reis Atlası, "'İstanbul 1992, s. 28; R. Şeşen, Onbeşinci Yüzyılda Tüıkçeye Tercümeler, s. 907. Eserin aslı için bkz. KZ, s. 1127-1128; İA, VI, 530; GAL, I, 481, S, 1, 882.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>2</th>
              <td>إبراهيم الفقير بن أحمد بن سليمان الكاتبي</td>
              <td>Ibrāhīm al-Faqīr b. Aḥmad b. Sulaymān al-Kātibī</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>[Not provided; should be in Arabic]</td>
              <td>Akdeniz Avrupa ve Karadeniz Havzaları Haritası (Portlandı)</td>
              <td>Arabic</td>
              <td>Harita</td>
              <td>MANUSCRIPT</td>
              <td>810 AH</td>
              <td>Hazine, nr. 1823</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>54x88(38x54) cm</td>
              <td>[Not provided]</td>
              <td>F. Karatay, TY, I, 464-465, nr. 1407</td>
              <td>Nil; Tuna; Akdeniz; Karadeniz ve sahilleri; Atlas Okyanusu kıyılarındaki Avrupa ve Afrika kıyıları; İngiltere; Batı Avrupa; Batı Afrika; Tunus</td>
              <td>İbrahim Hakkı (Konyalı), Topkapı Sarayında Deri Üzerine Yapılmış Eski\nHaritalar, İstanbul 1936, s. 258-261; The History of Cartography, II, s. 264-265.</td>
              <td>Work is unnamed in text; the text says that the author wrote a map of the Mediterranean and the Black Sea and their surroundings.</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>974 AH</td>
              <td>Reşid Efendi, nr. 69</td>
              <td>NaN</td>
              <td>Talikle</td>
              <td>yap. 1-32</td>
              <td>10,5x31(7,5x15) cm</td>
              <td>32 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>996 AH</td>
              <td>Hacı Beşir Ağa, nr. 656/32</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>yap. 152b-159b</td>
              <td>17,5x29,5(11,5x23,5) cm</td>
              <td>35 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>Unclear what page numbers mean</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>~900 AH</td>
              <td>Saliha Hatun, nr. 110/1</td>
              <td>NaN</td>
              <td>Nestalikle</td>
              <td>yap. 1b-94b</td>
              <td>14,5x21(10x15,5) cm</td>
              <td>18 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>Unclear what page numbers mean</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>~900 AH</td>
              <td>Hüsrev Paşa, nr. 431</td>
              <td>NaN</td>
              <td>Talikle</td>
              <td>47 yaprak</td>
              <td>12x19(6x13,2) cm</td>
              <td>21 str; Terceme-i Aca'ib al-Mahlukat Müellif çeşitli kitaplardan, kendi hatıralarından faydalanarak yazmıştır. Tashih görmüş.</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>1022 AH</td>
              <td>Vatican, Berg, nr. 27</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>40 yaprak</td>
              <td>15x20,5 cm</td>
              <td>19 str</td>
              <td>Katalog, s. 346.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>1023 AH</td>
              <td>Antalya, Tekelioğlu, nr. 775</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>81 yaprak</td>
              <td>14,5x20 (9,5x14) cm</td>
              <td>11 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>1025 AH (Safer)</td>
              <td>Wien, nr.1453</td>
              <td>NaN</td>
              <td>Talikle</td>
              <td>59 yaprak</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>G. Flugel, Die arabischen ..... türkischen Handsch ..... , II, 520-521.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>1028 AH</td>
              <td>Milli Kütüphane, A. 3028/1</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>yap. 1-79</td>
              <td>18,5x12,5(12,5x8) cm</td>
              <td>13 str; istinsahı Şeyhzade\r\nMehmed Harpüti tarafından</td>
              <td>MKAHYK, I, 12.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>1061 AH (29 Rebiülahir)</td>
              <td>Yapı Kredi, Sermet Çifter, nr. 808</td>
              <td>NaN</td>
              <td>Divani</td>
              <td>174 yaprak</td>
              <td>[Not provided]</td>
              <td>İstinsahı Sulayman b. İbrahim tarafından</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>1063 AH</td>
              <td>Yazma Bağışlar, nr. 2004</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>28 yaprak</td>
              <td>14x20,5 (8,7x15) cm</td>
              <td>27 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>1065 AH (Şaban)</td>
              <td>Vatican, TY, nr. 269</td>
              <td>NaN</td>
              <td>[Not provided]</td>
              <td>69 yaprak</td>
              <td>14x20 cm</td>
              <td>21 str</td>
              <td>E. Rossi, TY, s. 233.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>1065 AH</td>
              <td>Berlin, nr. 177</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>84 yaprak</td>
              <td>25x17 cm</td>
              <td>15 str</td>
              <td>W. Pertsch, s. 197-198.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>1092 AH</td>
              <td>Kemankeş, nr. 402/1</td>
              <td>NaN</td>
              <td>Talikle</td>
              <td>yap. 1b-23a</td>
              <td>14,5x20 cm</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>Unclear what page numbers mean</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>1099 (Zilhicce)</td>
              <td>Hacı Mahmud, nr. 5392</td>
              <td>NaN</td>
              <td>Talikle</td>
              <td>88 yaprak</td>
              <td>13,5x20,5 (8,6x13,5) cm</td>
              <td>13 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>~1000 AH</td>
              <td>British Museum, nr. 4088</td>
              <td>NaN</td>
              <td>[Not provided]</td>
              <td>73 yaprak</td>
              <td>[Not provided]</td>
              <td>13 str</td>
              <td>De Slane, Cat., s. 106-107.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>~1000 AH</td>
              <td>İstanbul Üniversitesi, TY, nr. 6806/2</td>
              <td>NaN</td>
              <td>Divani</td>
              <td>yap. 7b-46b</td>
              <td>12,7x18,4(9,5x15,2) cm</td>
              <td>15 str; Sonu eksik</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>Unclear what page numbers mean</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>~1000 AH</td>
              <td>Laleli, nr. 3722/1</td>
              <td>NaN</td>
              <td>Divani</td>
              <td>yap. 1b-22b</td>
              <td>15x20,8(11,4x16) cm</td>
              <td>17 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>Unclear what page numbers mean</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>~1000 AH</td>
              <td>Hacı Mahmud, nr. 4899/2</td>
              <td>NaN</td>
              <td>Talikle</td>
              <td>yap. 32b-62b</td>
              <td>14,7x21,7(8,8x14,4) cm</td>
              <td>17 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>Unclear what page numbers mean</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>~1000 AH</td>
              <td>Tahir Ağa, nr. 335/2</td>
              <td>NaN</td>
              <td>Divani</td>
              <td>yap. 17b-52a</td>
              <td>14,5x20,5(10,5x16,2) cm</td>
              <td>19 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>Unclear what page numbers mean</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>~1000 AH</td>
              <td>İzmir Milli, nr. 50/52-2</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>yap. 59b-97b</td>
              <td>12x19 (7x12) cm</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>Unclear what page numbers mean</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>1125 AH (11 Receb)</td>
              <td>İzmir nr. 740</td>
              <td>NaN</td>
              <td>Divani</td>
              <td>65 yaprak</td>
              <td>15x20,5 (9x16) cm</td>
              <td>13 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>1126 AH (Cemaziyelevvel)</td>
              <td>İstanbul Üniversitesi, TY, nr. 6797</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>51 yaprak</td>
              <td>14,5x19,8(7,8x14) cm</td>
              <td>15 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>1158 AH</td>
              <td>Yazma Bağışlar, nr. 2343</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>38 yaprak</td>
              <td>14,6x20,3(8,5x12,5) cm</td>
              <td>13 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>1184 AH</td>
              <td>İstanbul Üniversitesi, TY, nr. 6764</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>45 yaprak</td>
              <td>14,5x21(9x15,5) cm</td>
              <td>İstinsahı Ḥamza\r\nb. 'Ali al-'Acūl tarafından</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>~1100 AH</td>
              <td>Sermet Çifter, nr. 111</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>111 yaprak</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>~1100 AH</td>
              <td>Beyazit Umumi, nr. 8048</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>yap. 38b-76a</td>
              <td>14x20,5 cm</td>
              <td>sonu eksik</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>Unclear what page numbers mean</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>~1100 AH</td>
              <td>Muallim Cevdet, nr. K. 370</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>104 yaprak</td>
              <td>15x10(9,6x6,5)cm</td>
              <td>8 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>~1100 AH</td>
              <td>Beyazit Umumi, nr. 5498</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>93 yaprak</td>
              <td>8x14(6x10) cm</td>
              <td>11 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>~1100 AH</td>
              <td>Sarejovo, nr. 5872</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>54 yaprak</td>
              <td>20,5x14 cm</td>
              <td>[Not provided]</td>
              <td>Katalog, s. 439.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>1202 AH</td>
              <td>Yazma Bağışlar nr. 2343</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>38 yaprak</td>
              <td>15x21(9,5x15) cm</td>
              <td>21 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>1206 AH</td>
              <td>Sadberk Hanım, nr. yaz. 479</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>216 yaprak</td>
              <td>20,5x18,5(13x7,5) cm</td>
              <td>15 str; İstinsahı ʿOmar b. ʿOsmān b. Ibrāhīm tarafından.</td>
              <td>Sadberk Hamm Müzesi Kütübhanesi Yazma Eserler Kataloğu, nr. 587.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>1231 AH</td>
              <td>Kahire Üniversitesi, Türkı, nr. 3199</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>146 yaprak</td>
              <td>12,5x21,5 cm</td>
              <td>19 str; İstinsahı Ḥāfiz Mustafa b. al-Hacc Ahmed tarafından.</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>1232 AH (25 Cemaziyelevvel)</td>
              <td>İzmir, nr. 739</td>
              <td>NaN</td>
              <td>Nesihle vs Rika</td>
              <td>42 yaprak</td>
              <td>14x19(7x15) cm</td>
              <td>17 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>1248 (15 Rebiülevvel)</td>
              <td>Berlin, Ms. or. oct. nr. 2726</td>
              <td>NaN</td>
              <td>Talikle</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>Teil 6</td>
              <td>Götz, nr. 332 ve 490.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>1253 AH</td>
              <td>Raşid Efendi, Eki, nr. 26098</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>85 yaprak</td>
              <td>22,8x14,5 (14,5x7) cm</td>
              <td>13 str; İstinsahı Şaban Efendi tarafından.</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>1273 AH</td>
              <td>Sermet Çifter, nr. 966</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>108 yaprak</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>1275 AH</td>
              <td>İstanbul Üniversitesi, TY, nr. 648</td>
              <td>NaN</td>
              <td>Rika</td>
              <td>50 yaprak</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>~1200 AH</td>
              <td>Beyazıt Umumi, nr. 5498</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>93 yaprak</td>
              <td>11,5x16 (8x12) cm</td>
              <td>11 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>~1200 AH</td>
              <td>Tavşanlı Zeytinoğlu, nr. 386/1</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>yap. 1b-34b</td>
              <td>11,3x19,4 (7,8x15) cm</td>
              <td>19 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>Unclear what page numbers mean</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>~1200 AH</td>
              <td>Ali Emiri, Tarih, nr. 561</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>66 yaprak</td>
              <td>15x20,6(8,1x16,2) cm</td>
              <td>17 str; Başından\r\nsonundan eksik.</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>~1200 AH</td>
              <td>Esad Efendi, nr. 2498/3</td>
              <td>NaN</td>
              <td>Talikle</td>
              <td>yap. 130a-159a</td>
              <td>13,7x21,5 (8x16) cm</td>
              <td>19 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>Unclear what page numbers mean</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>[Not provided]</td>
              <td>Ali Emiri, TY, nr. 897/1</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>46 yaprak</td>
              <td>9,9x17 (5,8x11,7) cm</td>
              <td>17 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>[Not provided]</td>
              <td>Tavşanlı, Zeytinoğlu, nr. 689/2</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>yap. 73-96</td>
              <td>14,6x21,2 (10,2x16,2) cm</td>
              <td>15 str; Sonu eksik.</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>[Not provided]</td>
              <td>Tavşanlı, Zeytinoğlu, nr. 473/2</td>
              <td>NaN</td>
              <td>Talikle</td>
              <td>yap. 82-84</td>
              <td>14,8x24,2 (11x19,5) cm</td>
              <td>parça; 34 str.</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>[Not provided]</td>
              <td>Sohrweide, s. 147: Ms. Or. Quart 1988/7</td>
              <td>NaN</td>
              <td>[Not provided]</td>
              <td>yap. 302b-319b</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>Unclear what page numbers mean</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>[Not provided]</td>
              <td>Berlin, nr. 181</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>24 yaprak</td>
              <td>22x15,5 cm</td>
              <td>13 str</td>
              <td>W. Pertsch, s. 199-200.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>[Not provided]</td>
              <td>Tercüman Gazetesi, nr.127/8:</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>yap. 110b-147b</td>
              <td>18x11,2 (14,5x6,6) cm</td>
              <td>23 str</td>
              <td>Katalog, I, 369.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>Unclear what page numbers mean</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>[Not provided]</td>
              <td>Ulucami, nr. 1716.</td>
              <td>NaN</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>[Not provided]</td>
              <td>Kütahya, Vahıd Paşa, nr. 2180.</td>
              <td>NaN</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>عجائب المخلوقات</td>
              <td>ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>[Not provided]</td>
              <td>Çorum, nr. 3169.</td>
              <td>NaN</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1007 AH</td>
              <td>Hazine, nr. 427</td>
              <td>NaN</td>
              <td>Talikle</td>
              <td>130 yaprak</td>
              <td>9x15 cm</td>
              <td>19 str</td>
              <td>F. Karatay, TY, nr. 1322.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1030 AH</td>
              <td>Hacı Mahmud Efendi, nr. 1900</td>
              <td>NaN</td>
              <td>Talikle</td>
              <td>118 yaprak</td>
              <td>19,5x11,5(13,5x6,5) cm</td>
              <td>17 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1034 AH</td>
              <td>Raşid Efendi, nr. 1328</td>
              <td>NaN</td>
              <td>[Not provided]</td>
              <td>102 yaprak</td>
              <td>23,5x13,5(13x7) cm</td>
              <td>19 str</td>
              <td>Katalog, s. 15.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1040 AH</td>
              <td>Bibliotheque Nationale, nr.206</td>
              <td>NaN</td>
              <td>Talikle</td>
              <td>133 yaprak</td>
              <td>14x22,5 cm</td>
              <td>[Not provided]</td>
              <td>E. Blochet, Cat, I, 261-262.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1042 AH</td>
              <td>Koğuşlar, nr. 919</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>88 yaprak</td>
              <td>19x29 cm</td>
              <td>25 str; İstinsahı 'Abduṣṣamad b. 'Ali b.\nMuḥammed tarafından</td>
              <td>F. Karatay, TY, nr. 1323.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1045 AH</td>
              <td>Hazine, nr. 426</td>
              <td>NaN</td>
              <td>Talikle</td>
              <td>144 yaprak</td>
              <td>14,5x20 cm</td>
              <td>15 str</td>
              <td>F. Karatay, TY, nr. 1325.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1061 AH</td>
              <td>Nuruosmaniye, nr. 3022</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>199 yaprak</td>
              <td>14,7x20,1 (9,2x15,8) cm</td>
              <td>17 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1063 AH (29 Safer)</td>
              <td>Berlin, nr. 178</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>180 yaprak</td>
              <td>19,5x12,5 cm</td>
              <td>15 str; İstinsahı Muḥarrem b. Muṣṭafā tarafından</td>
              <td>W. Pertsch, s. 198-199.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1066 AH (Rebiülevvel)</td>
              <td>Wien nr. 1450</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>107 yaprak</td>
              <td>[Not provided]</td>
              <td>19 str</td>
              <td>Flügel, Die arabischen ............. turkischen zu Wien, 1865, II, 518.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1067 AH (Rebiülahir)</td>
              <td>İstanbul Üniversitesi, TY, nr. 6741</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>135 yaprak</td>
              <td>14x20(9x15) cm</td>
              <td>15 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1073 AH (Şevval)</td>
              <td>İstanbul Üniversitesi, TY, nr. 6785</td>
              <td>NaN</td>
              <td>[Not provided]</td>
              <td>73 yaprak</td>
              <td>13,5x19,5(9,3x16,2) cm</td>
              <td>21 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1077 AH (Şaban)</td>
              <td>Milli Kütüphane, AY, nr. 770</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>141 yaprak</td>
              <td>15,2x20,6(9,6x14,2) cm</td>
              <td>13 str</td>
              <td>Milli Kütüphane Yazmalar Kat, 1, 14.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1077 AH</td>
              <td>İzmir, nr. 419</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>91 yaprak</td>
              <td>20,5x14 (15,5x8) cm</td>
              <td>23 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1078 AH</td>
              <td>British Museum, Add., nr. 7895</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>114 yaprak</td>
              <td>[Not provided]</td>
              <td>19 str</td>
              <td>Cat. of the Turkish Mss. in the Brit. Mus. s. 105-106.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1092 AH</td>
              <td>Pertevniyal, nr.456</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>162 yaprak</td>
              <td>20x14,5(15x9,5) cm</td>
              <td>15 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1093 AH (22 Zilkade)</td>
              <td>Berlin, Ms. or. oct., nr. 1886</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>169 yaprak</td>
              <td>14x20,5(9,5x15,5) cm</td>
              <td>İstinsahı Kayyumzade Mustafa Çelebi tarafından</td>
              <td>Götz, nr. 333</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1098 AH (Muharrem)</td>
              <td>Saliha Hatun, nr. 112/1</td>
              <td>NaN</td>
              <td>Nestalikle</td>
              <td>yap. 1b-87a</td>
              <td>21x15(15,5x10) cm</td>
              <td>19 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>Unclear what page numbers mean</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>~1000 AH</td>
              <td>Bibliotheque Nationale, nr. 214</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>143 yaprak</td>
              <td>15x21,5 cm</td>
              <td>[Not provided]</td>
              <td>Blochet, Cat., I, 265.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>~1000 AH</td>
              <td>Reşid Efendi, nr. 785</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>114 yaprak</td>
              <td>10,5x18,5(6,5x14) cm</td>
              <td>19 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1122 AH</td>
              <td>Afyon, Gedik Ahmed nr.17170</td>
              <td>NaN</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>TÜYATOK, s.8</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1125 AH (Cemaziyelahir)</td>
              <td>İstanbul Üniversitesi, TY, nr. 2249</td>
              <td>NaN</td>
              <td>Talikle</td>
              <td>196 yaprak</td>
              <td>11,8x20,5(7x15) cm</td>
              <td>19 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1133 AH</td>
              <td>Vatican, TY, nr. 305</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>119 yaprak</td>
              <td>19,5x12,5 cm</td>
              <td>17 str</td>
              <td>E. Rossi, TY, s. 298.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1143 AH</td>
              <td>İstanbul Üniversitesi, TY, nr. 5874</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>139 yaprak</td>
              <td>13x19,8(9,5x16,1) cm</td>
              <td>17 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1149 AH</td>
              <td>Fatih, nr. 2615</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>89 yaprak</td>
              <td>20,3x14,8(16,9xbb) cm</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>Unclear what "bb" refers to</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1164 AH</td>
              <td>Serez nr. 1641</td>
              <td>NaN</td>
              <td>[Not provided]</td>
              <td>74 yaprak</td>
              <td>22x16,6(bbxbb) cm</td>
              <td>bb. str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>Unclear what "bb" refers to</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1168 AH</td>
              <td>Revan Köşkü, nr. 1656</td>
              <td>NaN</td>
              <td>Talikle</td>
              <td>144 yaprak</td>
              <td>11,4x18,4 cm</td>
              <td>15 str</td>
              <td>F. Karatay, TY, nr. 1324.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1177 AH (Cemaziyelevvel)</td>
              <td>İstanbul Üniversitesi, TY, nr. 6695</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>150 yaprak</td>
              <td>12,7x19,3(7,6x14,2) cm</td>
              <td>19 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1186 AH</td>
              <td>Pertevniyal, nr. 454</td>
              <td>NaN</td>
              <td>Talikle</td>
              <td>56 yaprak</td>
              <td>19,3x13(15,5x8,2) cm</td>
              <td>23 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>~1100 AH</td>
              <td>İstanbul Üniversitesi, TY, nr. 2337</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>120 yaprak</td>
              <td>9x16(4,7x15) cm</td>
              <td>25 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1210 AH (Cemaziyelahir)</td>
              <td>İstanbul Üniversitesi, TY, nr. 6702</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>204 yaprak</td>
              <td>12x17,8(7x12,5) cm</td>
              <td>13 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1233 AH</td>
              <td>Mevlana Müzesi, nr. 1059</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>117 yaprak</td>
              <td>15,5x23,8(12,3x17,8) cm</td>
              <td>15 str</td>
              <td>Abdülbaki Gölpınarlı, Mevlana Müzesi Yazmalar Kat, nr. 1642.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1236 AH (15 Receb)</td>
              <td>Milli Kütüphane, AY, nr. 4388/1</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>yap. 1b-251b</td>
              <td>14,5x21 (10,5x15,5) cm</td>
              <td>15 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>Unclear what page numbers mean</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1254 AH</td>
              <td>İstanbul Üniversitesi, TY, nr. 846</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>110 yaprak</td>
              <td>11,5x17,6(5,8x11,5) cm</td>
              <td>15 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1260 AH</td>
              <td>İstanbul Üniversitesi, TY, nr, 6742</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>125 yaprak</td>
              <td>14,4x22,5(9x17) cm</td>
              <td>17 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1262 AH (20 Şaban)</td>
              <td>Berlin, Ms. Or . Oct. 2777</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>92 yaprak</td>
              <td>23x14(15x7) cm</td>
              <td>21 str; İstinsahı Ḥasan al-\r\nHalvatī Tilmīẕī M. Rāsī tarafından</td>
              <td>Sohrweide, III, 165-166.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1273 AH</td>
              <td>Hacı Mahmud Efendi, nr. 1856</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>102 yaprak</td>
              <td>19x11 (15x7,5) cm</td>
              <td>19 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>1287 AH</td>
              <td>İstanbul Üniversitesi, TY, nr, 6743</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>134 yaprak</td>
              <td>13,5x18,8(9,5x14,8) cm</td>
              <td>15 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>~1200 AH</td>
              <td>Pertevniyal, nr. 455</td>
              <td>NaN</td>
              <td>Rika</td>
              <td>137 yaprak</td>
              <td>19,3x14,5(12x8) cm</td>
              <td>15 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>[Not provided]</td>
              <td>Kahire Üniversitesi, Türkı, nr. 6982</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>245 yaprak</td>
              <td>9x17 cm</td>
              <td>25 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>[Not provided]</td>
              <td>Berlin, Ms.or. oct., nr. 2530</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>134 yaprak</td>
              <td>15x21,5(11x17) cm</td>
              <td>[Not provided]</td>
              <td>Götz, nr. 334.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>[Not provided]</td>
              <td>Elmalı, nr. 2941/2</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>yap. 27b-32a</td>
              <td>16,5x22,8(11x18) cm</td>
              <td>20 str</td>
              <td>TÜYATOK, III, 121-122</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>Unclear what page numbers mean</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>[Not provided]</td>
              <td>Bosnian Institute, nr. 544 Ms.119</td>
              <td>NaN</td>
              <td>[Not provided]</td>
              <td>76 yaprak</td>
              <td>16x22,5 cm</td>
              <td>21 str</td>
              <td>Cat. of Arabic-Persian-Turkish Ms. Bosnian..., Zurich 1997, I, 323-324</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>[Not provided]</td>
              <td>B. Flemming, Hs. Or. Oct. 922/2</td>
              <td>NaN</td>
              <td>[Not provided]</td>
              <td>yap. 133b-232a</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>Katalog, I, 237.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>Unclear what page numbers mean</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>[Not provided]</td>
              <td>Koyunoğlu, nr.10204</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>110 yaprak</td>
              <td>22x12,5 cm</td>
              <td>19 str</td>
              <td>Koyunoğlu Kataloğu, s. 14</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>[Not provided]</td>
              <td>Koyunoğlu, nr.10962</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>127 yaprak</td>
              <td>20,6x15,5 cm</td>
              <td>15 str; İstinsahı Abdülḥalīm b. İbrāhīm tarafından.</td>
              <td>Koyunoğlu Kataloğu, s. 14.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>[Not provided]</td>
              <td>Milli Kütüphane, AY, nr. 2676</td>
              <td>NaN</td>
              <td>Talikle ve Nesihle</td>
              <td>90 yaprak</td>
              <td>12x20,5(7x16) cm</td>
              <td>23 str</td>
              <td>Milli Kütüphane Yazmalar Kat., I, 15.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>[Not provided]</td>
              <td>Milli Kütüphane, AY, nr.2757</td>
              <td>NaN</td>
              <td>Talikle</td>
              <td>84 yaprak</td>
              <td>14,3x20(6,7x15,2) cm</td>
              <td>23 str</td>
              <td>Milli Kütüphane Yazmalar Kat., I, 16.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>[Not provided]</td>
              <td>Osman Huldi Öztürkler, nr. 52/1</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>1b-167b yaprak</td>
              <td>20x15 (15x10,5) cm</td>
              <td>13 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>Unclear what page numbers mean</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>[Not provided]</td>
              <td>Wienne, nr. 1450</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>107 yaprak</td>
              <td>7,5x5,5 cm</td>
              <td>19 str</td>
              <td>Flugel, 11, 519-520.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>[Not provided]</td>
              <td>Karaman, nr. 1150/6</td>
              <td>NaN</td>
              <td>[Not provided]</td>
              <td>yap. 80b-147b</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>Ali Berberoğlu, Karaman Yazmaları Kataloğu, s. 10.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>Unclear what page numbers mean</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>[Not provided]</td>
              <td>Sohrweide, s.147-148: Ms. Or. quart nr. 1988/30</td>
              <td>NaN</td>
              <td>[Not provided]</td>
              <td>yap. 510b-523a.</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>Unclear what page numbers mean</td>
            </tr>
            <tr>
              <th>3</th>
              <td>أحمد بيجان</td>
              <td>Aḥmed Bīcān</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>در مكنون</td>
              <td>Dürr-i Meknūn</td>
              <td>Turkish</td>
              <td>[Unlisted in Genre Tab]</td>
              <td>MANUSCRIPT</td>
              <td>[Not provided]</td>
              <td>Berlin, nr.180</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>113 yaprak</td>
              <td>22x15 cm</td>
              <td>15 str</td>
              <td>W. Pertsch, s.199.</td>
              <td>[Not provided]</td>
              <td>ŞN, s. 111; Mecdi, s. 128; OM, 1, 16; Franz Taeschner, 'Die Geographische\r\nLiteratur der Osmanen', ZDMG N. F. 2, LXXVII, 1923, s. 36-38;GAL, S. I, 882; İA, I, 181-182,VI, 530; V. L. Menage, "Bidjan", EI2, I, 1202; Türk Meşhurları, s. 19; Adıvar, s. 29; G. Kut, aynı makale, s. 190; DİA, I, 316-317; Götz, nr. 332; Şeşen, aynı yer; Amil Çelebioğlu, "Ahmed\r\nRican", DİA, il, 49-51; Semavi Eyice, "Ahmed Bican Türbesi", DİA, il, 52.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>4</th>
              <td>إبراهيم المرسي</td>
              <td>Ibrāhīm al-Mursī</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>[Not provided; should be in Arabic]</td>
              <td>Mursiyeli İbrahim'in 1461 Tarihli\nHaritası</td>
              <td>Arabic</td>
              <td>Harita</td>
              <td>MANUSCRIPT</td>
              <td>865 AH</td>
              <td>Deniz Müzesi, 1 nolu ana envanter defteri, nr. 882</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>90x53(89x48) cm</td>
              <td>Haritanın etrafında 1 cm. genişliğinde motiflerle süslü bir\r\nbordür vardır.</td>
              <td>[Not provided]</td>
              <td>Akdeniz, Karadeniz sahillerini; Batı Avrupa kıyılarını; İngiliz Adalarını.</td>
              <td>Doğan Uçar, "Mürsiyeli İbrahim'in Haritası", Birinci Uluslararası Türkİslam\nBilim ve Teknoloji Tarihi Kongresi Bildirileri, nşr. Kazım Çeçen, İstanbul 1981, III, 185-189; W. Laitner, Der Portuland des Tabib Ibrahim el-Mursi vom jahr 1461. Festschrift zur 100-jahrfeier des Österreichischen St. Georg Callegs in Istanbul, Türkei, İstanbul 1982; The History of Cartography, II, s. 264- 266.</td>
              <td>Work is unnamed in text; the name in the text is based off of a paper presented by a Turkish academic</td>
            </tr>
            <tr>
              <th>5</th>
              <td>[Not provided; should be in Greek]</td>
              <td>AMÎRUTZES VE OĞLU MEHMED</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>ترجمة جغرافية بطلميوس</td>
              <td>Tarjamat Jughrāfiyyat Baṭlimiyūs</td>
              <td>Arabic</td>
              <td>Terceme; Coğrafya</td>
              <td>MANUSCRIPT</td>
              <td>1465 CE</td>
              <td>Ayasofya, nr. 2610</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>129 yaprak</td>
              <td>12x17,2(8x12,7) cm</td>
              <td>haritaları mükemmel; Fatih devrinde istinsah edilmiş orjinal nüshadır.</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>KZ, s.590; H. Ritter, "Rezension zu Bibliothek Arabischer Historiker und\nGeographen herausgegeben von Hans v. Mzik", Der İslam, XIX, 1931, s.53-54; Adıvar, s.34-\n36, bilhassa 2. not; J. H. Kramers, "Coğrafya", İA, III, 205-206; DSB, XI, 186-206; Bagrow,\nLeo,"A Tale from the Bosphorus", Imago Mundi, XII, 1955, s. 26-27; Dünden Bügüne İstanbul\nAnsiklopedisi, I, 246-247; DİA ,VIII, 63.</td>
              <td>Translation ordered by Sultan Mehmed II; Original version of author's name is not provided</td>
            </tr>
            <tr>
              <th>5</th>
              <td>[Not provided; should be in Greek]</td>
              <td>AMÎRUTZES VE OĞLU MEHMED</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>ترجمة جغرافية بطلميوس</td>
              <td>Tarjamat Jughrāfiyyat Baṭlimiyūs</td>
              <td>Arabic</td>
              <td>Terceme; Coğrafya</td>
              <td>MANUSCRIPT</td>
              <td>~1000 AH</td>
              <td>Ayasofya, nr. 2596</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>75 yaprak</td>
              <td>28x39,5(19,5x25) cm</td>
              <td>Haritaları eksik</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>KZ, s.590; H. Ritter, "Rezension zu Bibliothek Arabischer Historiker und\r\nGeographen herausgegeben von Hans v. Mzik", Der İslam, XIX, 1931, s.53-54; Adıvar, s.34-\r\n36, bilhassa 2. not; J. H. Kramers, "Coğrafya", İA, III, 205-206; DSB, XI, 186-206; Bagrow,\r\nLeo,"A Tale from the Bosphorus", Imago Mundi, XII, 1955, s. 26-27; Dünden Bügüne İstanbul\r\nAnsiklopedisi, I, 246-247; DİA ,VIII, 63.</td>
              <td>Translation ordered by Sultan Mehmed II; Original version of author's name is not provided</td>
            </tr>
            <tr>
              <th>6</th>
              <td>ركن الدين أحمد</td>
              <td>RUKNUDDDIN AHMED</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>ترجمهء عجائب المخلوقات</td>
              <td>Terceme-i ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>Terceme; ‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>852 AH</td>
              <td>Ali Emiri, Türki-Tarih, nr. 897</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>324 yaprak</td>
              <td>17,2x24,8(13,8x21) cm</td>
              <td>17 str; İstinsahı 'Alauddin b. 'Abdulkarim tarafından Yenişehir'de.</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>Adıvar, s.29; Uzunçarşılı, Osmanlı Tarihi, Ankara 1972, II, 537; Blochet,\r\nII, 139; G. Kut, aynı makale, s. 188-190; DİA, I, 316-317; Şeşen, aynı yer.</td>
              <td>Original Arabic for author's name is not provided; Arabic is reverse engineered from the Turkish name written in the text</td>
            </tr>
            <tr>
              <th>6</th>
              <td>ركن الدين أحمد</td>
              <td>RUKNUDDDIN AHMED</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>ترجمهء عجائب المخلوقات</td>
              <td>Terceme-i ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>Terceme; ‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>1103 AH</td>
              <td>Nuri Arlasez, nr.128:</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>403 yaprak</td>
              <td>19x28,8 (12,8x21,1) cm</td>
              <td>15 str; İstinsahı\nMuḥammed b. Muḥammed tarafından</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>Adıvar, s.29; Uzunçarşılı, Osmanlı Tarihi, Ankara 1972, II, 537; Blochet,\r\nII, 139; G. Kut, aynı makale, s. 188-190; DİA, I, 316-317; Şeşen, aynı yer.</td>
              <td>Original Arabic for author's name is not provided; Arabic is reverse engineered from the Turkish name written in the text</td>
            </tr>
            <tr>
              <th>6</th>
              <td>ركن الدين أحمد</td>
              <td>RUKNUDDDIN AHMED</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>ترجمهء عجائب المخلوقات</td>
              <td>Terceme-i ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>Terceme; ‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>~1100 AH</td>
              <td>Bibliotheque Nationale, TY, nr.1338</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>266 yaprak</td>
              <td>20,5x30 cm</td>
              <td>[Not provided]</td>
              <td>E. Blochet, Cat. des Mss. turcs, II, 238 nr.1339; Süleymaniye mikrofilm arşivi nr.3234.</td>
              <td>[Not provided]</td>
              <td>Adıvar, s.29; Uzunçarşılı, Osmanlı Tarihi, Ankara 1972, II, 537; Blochet,\r\nII, 139; G. Kut, aynı makale, s. 188-190; DİA, I, 316-317; Şeşen, aynı yer.</td>
              <td>Original Arabic for author's name is not provided; Arabic is reverse engineered from the Turkish name written in the text</td>
            </tr>
            <tr>
              <th>6</th>
              <td>ركن الدين أحمد</td>
              <td>RUKNUDDDIN AHMED</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>ترجمهء عجائب المخلوقات</td>
              <td>Terceme-i ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>Terceme; ‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>~1100 AH</td>
              <td>Düğümlü Baba, nr.556</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>165 yaprak</td>
              <td>14,5x20,5(9x14,5) cm</td>
              <td>15 str</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>Adıvar, s.29; Uzunçarşılı, Osmanlı Tarihi, Ankara 1972, II, 537; Blochet,\r\nII, 139; G. Kut, aynı makale, s. 188-190; DİA, I, 316-317; Şeşen, aynı yer.</td>
              <td>Original Arabic for author's name is not provided; Arabic is reverse engineered from the Turkish name written in the text</td>
            </tr>
            <tr>
              <th>6</th>
              <td>ركن الدين أحمد</td>
              <td>RUKNUDDDIN AHMED</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>ترجمهء عجائب المخلوقات</td>
              <td>Terceme-i ʿAcāʾib al-Mahlūḳāt</td>
              <td>Turkish</td>
              <td>Terceme; ‘Acâ’ib al-Mahlûkât</td>
              <td>MANUSCRIPT</td>
              <td>1262 AH</td>
              <td>Beyazıt Umumi, nr.14124</td>
              <td>NaN</td>
              <td>Nesihle</td>
              <td>404 yaprak</td>
              <td>16,5x23,5 cm</td>
              <td>17 str; İstinsahı 'Oşman b.\r\nṢāliḥ tarafından</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>Adıvar, s.29; Uzunçarşılı, Osmanlı Tarihi, Ankara 1972, II, 537; Blochet,\r\nII, 139; G. Kut, aynı makale, s. 188-190; DİA, I, 316-317; Şeşen, aynı yer.</td>
              <td>Original Arabic for author's name is not provided; Arabic is reverse engineered from the Turkish name written in the text</td>
            </tr>
            <tr>
              <th>7</th>
              <td>سيّد علي أكبر خطائي</td>
              <td>Sayyid ʿAlī Akbar Khaṭāʾī</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>خطاي نامه</td>
              <td>Khaṭāy Nāmah</td>
              <td>Persian</td>
              <td>Hıtây-nâme</td>
              <td>MANUSCRIPT</td>
              <td>922 AH (Rebiülevvel)</td>
              <td>Aşir Efendi, nr.249</td>
              <td>NaN</td>
              <td>Talikle</td>
              <td>125 yaprak</td>
              <td>15x21,2(8x12) cm</td>
              <td>11 str</td>
              <td>[Not provided]</td>
              <td>Çin</td>
              <td>P. Kahle, "Eine Islamische Quelle uber China um 1500 (das Chitay-name\r\ndes 'Ali Ekber)",Oostersch Genoots. In Nederland, 7 de Cong., 1933 s.21-22; aynı müellif,\r\n"İslamichen Quellen zum Chinesischen Porzellan", ZDMG, 1934, 99, s. 35 vd.; aynı müellif,\r\n"Eine Islamische Quelle uber China um 1500 (Das Khitayname des 'Ali Ekber.)", Acta\r\nOrientalia, 12 (1934) s. 91-110; aynı müellif, "Türk Coğrafyacılarının Tasvirine Göre Çin",\r\nİslam Tedkikleri Enstitüsü Dergisi, c. II, cüz. 1, İstanbul 1957, s. 96-97; İA, I, 318-319; Storey,\r\nPersian Literature, I, 1970-1977, s. 431-432,; Meydan Larousse, I, 316; Büyük Larousse, I,\r\n381; İsmail Aka, "Hıtay Sefaretnamesi", Belleten L/197(1986), s. 603-605; DİA, VIII, 63;-\Kemal\r\nÖzdemir, aynı eser, s. 28.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>7</th>
              <td>سيّد علي أكبر خطائي</td>
              <td>Sayyid ʿAlī Akbar Khaṭāʾī</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>خطاي نامه</td>
              <td>Khaṭāy Nāmah</td>
              <td>Persian</td>
              <td>Hıtây-nâme</td>
              <td>MANUSCRIPT</td>
              <td>[Not provided]</td>
              <td>Leiden, nr. 919, III, s.9.</td>
              <td>NaN</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>Son kısmı eksik</td>
              <td>[Not provided]</td>
              <td>Çin</td>
              <td>P. Kahle, "Eine Islamische Quelle uber China um 1500 (das Chitay-name\r\ndes 'Ali Ekber)",Oostersch Genoots. In Nederland, 7 de Cong., 1933 s.21-22; aynı müellif,\r\n"İslamichen Quellen zum Chinesischen Porzellan", ZDMG, 1934, 99, s. 35 vd.; aynı müellif,\r\n"Eine Islamische Quelle uber China um 1500 (Das Khitayname des 'Ali Ekber.)", Acta\r\nOrientalia, 12 (1934) s. 91-110; aynı müellif, "Türk Coğrafyacılarının Tasvirine Göre Çin",\r\nİslam Tedkikleri Enstitüsü Dergisi, c. II, cüz. 1, İstanbul 1957, s. 96-97; İA, I, 318-319; Storey,\r\nPersian Literature, I, 1970-1977, s. 431-432,; Meydan Larousse, I, 316; Büyük Larousse, I,\r\n381; İsmail Aka, "Hıtay Sefaretnamesi", Belleten L/197(1986), s. 603-605; DİA, VIII, 63;-\Kemal\r\nÖzdemir, aynı eser, s. 28.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>7</th>
              <td>سيّد علي أكبر خطائي</td>
              <td>Sayyid ʿAlī Akbar Khaṭāʾī</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>خطاي نامه</td>
              <td>Khaṭāy Nāmah</td>
              <td>Persian</td>
              <td>Hıtây-nâme</td>
              <td>MANUSCRIPT</td>
              <td>~1215 AH</td>
              <td>Bibliotheque Nationale, Supp. Turc, nr. 1130</td>
              <td>NaN</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>Aşir Efendi nüshasından kopya edilmiştir.</td>
              <td>Blochet, I, 521.</td>
              <td>Çin</td>
              <td>P. Kahle, "Eine Islamische Quelle uber China um 1500 (das Chitay-name\r\ndes 'Ali Ekber)",Oostersch Genoots. In Nederland, 7 de Cong., 1933 s.21-22; aynı müellif,\r\n"İslamichen Quellen zum Chinesischen Porzellan", ZDMG, 1934, 99, s. 35 vd.; aynı müellif,\r\n"Eine Islamische Quelle uber China um 1500 (Das Khitayname des 'Ali Ekber.)", Acta\r\nOrientalia, 12 (1934) s. 91-110; aynı müellif, "Türk Coğrafyacılarının Tasvirine Göre Çin",\r\nİslam Tedkikleri Enstitüsü Dergisi, c. II, cüz. 1, İstanbul 1957, s. 96-97; İA, I, 318-319; Storey,\r\nPersian Literature, I, 1970-1977, s. 431-432,; Meydan Larousse, I, 316; Büyük Larousse, I,\r\n381; İsmail Aka, "Hıtay Sefaretnamesi", Belleten L/197(1986), s. 603-605; DİA, VIII, 63;-\Kemal\r\nÖzdemir, aynı eser, s. 28.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>7</th>
              <td>سيّد علي أكبر خطائي</td>
              <td>Sayyid ʿAlī Akbar Khaṭāʾī</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>خطاي نامه</td>
              <td>Khaṭāy Nāmah</td>
              <td>Turkish</td>
              <td>Hıtây-nâme</td>
              <td>MANUSCRIPT</td>
              <td>[Not provided]</td>
              <td>Ayasofya, nr. 3188</td>
              <td>NaN</td>
              <td>Talikle</td>
              <td>155 yaprak</td>
              <td>12,5x19(7,5x11,1) cm</td>
              <td>12 str</td>
              <td>[Not provided]</td>
              <td>Çin</td>
              <td>P. Kahle, "Eine Islamische Quelle uber China um 1500 (das Chitay-name\r\ndes 'Ali Ekber)",Oostersch Genoots. In Nederland, 7 de Cong., 1933 s.21-22; aynı müellif,\r\n"İslamichen Quellen zum Chinesischen Porzellan", ZDMG, 1934, 99, s. 35 vd.; aynı müellif,\r\n"Eine Islamische Quelle uber China um 1500 (Das Khitayname des 'Ali Ekber.)", Acta\r\nOrientalia, 12 (1934) s. 91-110; aynı müellif, "Türk Coğrafyacılarının Tasvirine Göre Çin",\r\nİslam Tedkikleri Enstitüsü Dergisi, c. II, cüz. 1, İstanbul 1957, s. 96-97; İA, I, 318-319; Storey,\r\nPersian Literature, I, 1970-1977, s. 431-432,; Meydan Larousse, I, 316; Büyük Larousse, I,\r\n381; İsmail Aka, "Hıtay Sefaretnamesi", Belleten L/197(1986), s. 603-605; DİA, VIII, 63;-\Kemal\r\nÖzdemir, aynı eser, s. 28.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>7</th>
              <td>سيّد علي أكبر خطائي</td>
              <td>Sayyid ʿAlī Akbar Khaṭāʾī</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>خطاي نامه</td>
              <td>Khaṭāy Nāmah</td>
              <td>Turkish</td>
              <td>Hıtây-nâme</td>
              <td>MANUSCRIPT</td>
              <td>995 AH (17 Zilhicce)</td>
              <td>Esad Efendi, nr. 1852</td>
              <td>NaN</td>
              <td>Talikle</td>
              <td>119 yaprak</td>
              <td>11x17,5(6,5x12,5) cm</td>
              <td>13 str</td>
              <td>[Not provided]</td>
              <td>Çin</td>
              <td>P. Kahle, "Eine Islamische Quelle uber China um 1500 (das Chitay-name\r\ndes 'Ali Ekber)",Oostersch Genoots. In Nederland, 7 de Cong., 1933 s.21-22; aynı müellif,\r\n"İslamichen Quellen zum Chinesischen Porzellan", ZDMG, 1934, 99, s. 35 vd.; aynı müellif,\r\n"Eine Islamische Quelle uber China um 1500 (Das Khitayname des 'Ali Ekber.)", Acta\r\nOrientalia, 12 (1934) s. 91-110; aynı müellif, "Türk Coğrafyacılarının Tasvirine Göre Çin",\r\nİslam Tedkikleri Enstitüsü Dergisi, c. II, cüz. 1, İstanbul 1957, s. 96-97; İA, I, 318-319; Storey,\r\nPersian Literature, I, 1970-1977, s. 431-432,; Meydan Larousse, I, 316; Büyük Larousse, I,\r\n381; İsmail Aka, "Hıtay Sefaretnamesi", Belleten L/197(1986), s. 603-605; DİA, VIII, 63;-\Kemal\r\nÖzdemir, aynı eser, s. 28.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>7</th>
              <td>سيّد علي أكبر خطائي</td>
              <td>Sayyid ʿAlī Akbar Khaṭāʾī</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>خطاي نامه</td>
              <td>Khaṭāy Nāmah</td>
              <td>Turkish</td>
              <td>Hıtây-nâme</td>
              <td>MANUSCRIPT</td>
              <td>[Not provided]</td>
              <td>Berlin, nr. 183</td>
              <td>NaN</td>
              <td>Nestalikle</td>
              <td>85 yaprak</td>
              <td>21x12 cm</td>
              <td>117 str</td>
              <td>W. Pertsch, s. 200-203</td>
              <td>Çin</td>
              <td>P. Kahle, "Eine Islamische Quelle uber China um 1500 (das Chitay-name\r\ndes 'Ali Ekber)",Oostersch Genoots. In Nederland, 7 de Cong., 1933 s.21-22; aynı müellif,\r\n"İslamichen Quellen zum Chinesischen Porzellan", ZDMG, 1934, 99, s. 35 vd.; aynı müellif,\r\n"Eine Islamische Quelle uber China um 1500 (Das Khitayname des 'Ali Ekber.)", Acta\r\nOrientalia, 12 (1934) s. 91-110; aynı müellif, "Türk Coğrafyacılarının Tasvirine Göre Çin",\r\nİslam Tedkikleri Enstitüsü Dergisi, c. II, cüz. 1, İstanbul 1957, s. 96-97; İA, I, 318-319; Storey,\r\nPersian Literature, I, 1970-1977, s. 431-432,; Meydan Larousse, I, 316; Büyük Larousse, I,\r\n381; İsmail Aka, "Hıtay Sefaretnamesi", Belleten L/197(1986), s. 603-605; DİA, VIII, 63;-\Kemal\r\nÖzdemir, aynı eser, s. 28.</td>
              <td>NaN</td>
            </tr>
            <tr>
              <th>7</th>
              <td>سيّد علي أكبر خطائي</td>
              <td>Sayyid ʿAlī Akbar Khaṭāʾī</td>
              <td>NaN</td>
              <td>NaN</td>
              <td>خطاي نامه</td>
              <td>Khaṭāy Nāmah</td>
              <td>Turkish</td>
              <td>Hıtây-nâme</td>
              <td>MANUSCRIPT</td>
              <td>1081 AH</td>
              <td>Dresden, nr. 71</td>
              <td>NaN</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>[Not provided]</td>
              <td>Çin</td>
              <td>P. Kahle, "Eine Islamische Quelle uber China um 1500 (das Chitay-name\r\ndes 'Ali Ekber)",Oostersch Genoots. In Nederland, 7 de Cong., 1933 s.21-22; aynı müellif,\r\n"İslamichen Quellen zum Chinesischen Porzellan", ZDMG, 1934, 99, s. 35 vd.; aynı müellif,\r\n"Eine Islamische Quelle uber China um 1500 (Das Khitayname des 'Ali Ekber.)", Acta\r\nOrientalia, 12 (1934) s. 91-110; aynı müellif, "Türk Coğrafyacılarının Tasvirine Göre Çin",\r\nİslam Tedkikleri Enstitüsü Dergisi, c. II, cüz. 1, İstanbul 1957, s. 96-97; İA, I, 318-319; Storey,\r\nPersian Literature, I, 1970-1977, s. 431-432,; Meydan Larousse, I, 316; Büyük Larousse, I,\r\n381; İsmail Aka, "Hıtay Sefaretnamesi", Belleten L/197(1986), s. 603-605; DİA, VIII, 63;-\Kemal\r\nÖzdemir, aynı eser, s. 28.</td>
              <td>NaN</td>
            </tr>
          </tbody>
        </table>

      <div class="dataTable-bottom">
      </div>
      <script language="JavaScript" type="text/javascript" src="https://ajax.aspnetcdn.com/ajax/jQuery/jquery-3.5.1.min.js"></script>
      <script language="JavaScript" type="text/javascript" src="https://cdn.datatables.net/1.12.1/js/jquery.dataTables.min.js"></script>
      <script language="JavaScript" type="text/javascript" src="https://cdn.datatables.net/plug-ins/1.12.1/api/fnFilterClear.js"></script>


    </div> <!-- clearfix, contains sidebar and table -->

    <script>
      /* Creating the filter category buttons -- slicing might not be the best but ah well*/

      /* Turkish letters */
      var letters = ['â','ç','ğ','ı','İ','î', 'ö', 'ş', 'ü', 'û'];
      for (var i = 0; i<letters.length; i++){
        document.getElementById("turkish-letters").innerHTML += `<button type='button' class = 'button-default' onclick='input(letters[${i}]) '>` + letters[i] + "</button>";
      }

      var type = ['Manuscript', 'Print'];
      for (var i = 0; i< type.length; i++){
        document.getElementById("filter-type").innerHTML += `<label class="label-checkbox" id="${type[i]}-9"><input type="checkbox"><span>`+ type[i] + '</span></label>';
      }

      var language = ['Turkish', 'Arabic'];
      for (var i = 0; i< language.length; i++){
        document.getElementById("lang").innerHTML += `<label class="label-checkbox" id="${language[i]}-7"><input type="checkbox"><span>`+ language[i] + '</span></label>';    
      }

      var script = ['Nesihle', 'Talikle', 'Rika', 'Divani', 'Küçük boy', 'Nestalikle'];
      for (var i = 0; i< script.length; i++){
        document.getElementById("script").innerHTML += `<label class="label-checkbox" id="${script[i]}-13"><input type="checkbox"><span>`+ script[i] + '</span></label>';    
      }

      var genres = [['Ottoman Keyword', 'Arabic Keyword ', 'Modern Turkish Keyword', 'English Keyword', 'French Keyword'], ['‘Acâ’ib', 'عجائب', 'Hayret verici şeyler', 'Wonders', 'Merveilles'], ['‘Acâibnâme', 'عجائبنامه', 'Hayret Verici Şeyler Kitabi', 'Book of Wonders', 'Livre des Merveilles '], ['‘Avd', 'عود', 'Iade', 'Return', 'Retour '], ['‘İbret-nümâ', 'عبرتنامه', 'İbret Kitabı', 'The Book of Lessons/Advices', 'Livre de Leçon'], ['A‘lâm (sing. Âlem)', 'أعلام', 'Alemler', 'worlds', 'Mondes'], ['A‘vân', 'أعوان', 'Zaman', 'Time', 'Temps'], ['Acâ’ib al-Arz va’l-Buldân', 'عجائب الأرض والبلدان', "Arz ve Ülkelerr'in Hayret Verici Şeyler", 'Wonders of the Earth and the Countries', 'Merveilles de la Terre et des États'], ['Acâ’ib al-Mahlükât; ‘Acâ’ib al-Mahlûkât', 'عجائب المخلوقات', 'Yaratılmış Garip, Harika Şeyler, Kozmoğrafya', 'Wonders of Creation, Cosmography', 'Merveilles de la Creation, Cosmographie'], ['Afrika', '', 'Afrika', 'Africa', "l'Afrique"], ['Ahbâr', 'أخبار', 'Ahbar, Haberler ', 'Chronicle ', 'Chronique '], ['âhval', 'أحوال', 'Durumlar/Haberler', 'Events, Situations', 'Evénement'], ['Ahval; Ahvâl', 'أحوال', 'Rehnümâ', 'Conditions', 'Conditions '], ['al-İşârât ', 'الإشارات', 'Işaretler ', 'Landmarks', 'Points de repère'], ['Amelî', 'عملي', 'Uygulamalı', 'applied', 'Pratique'], ['Amerika', '', 'Amerika', 'America', "l'Amérique"], ['Amsâr ', 'أمصار', 'Bölgeler ', 'Territories', 'Territoires '], ['Arazî', 'أراضي', 'Arazi', 'Lands', 'Terres '], ['Arz', 'أرض', 'Yeryüzü', 'Earth', 'Terre'], ['Askeri', 'عسكري', 'Askeri', 'Military', 'Militaire'], ['Asya', '', 'Asya', 'Asia', "l'Asie"], ['Atlas', 'أطلس', 'Atlas', 'Atlas', 'Atlas '], ['Atlaslı Coğrafya', 'آطلسلي جغرافيا', 'Atlaslı Coğrafya', 'Geography with atlas', 'Géographie avec atlas'], ['Avrupa', '', 'Avrupa', 'Europe', "l'Europe"], ['Beyân', 'بيان', 'İfade etme/Bildirme', 'Statement', 'Déclaration'], ['Bilâd', 'بلاد', 'Beldeler', 'Lands/Countries/Towns', 'Pays/Villes'], ['Ceb', 'جيب', 'Cep', 'Pocket', 'Poche'], ['Cevelan', 'جولان', 'Gezinti', 'Travel', 'Voyage'], ['Cihan', 'جهان', 'Cihan', 'World', 'Monde'], ['Cihannümâ', 'جهاننما', 'Dünya Kitabı', 'Book of the World', 'Livre du Monde '], ['Coğrafya ', 'جغرافية', 'Coğrafya', 'Geography', 'Géographie'], ['Coğrafya Muallimi', 'جغرافيا معلمي', 'Coğrafya Öğretmeni', 'Geography teacher', 'Enseignant de géographie'], ['Dağ', 'داغ', 'Dağ', 'Mountain', 'Montagne'], ['Dalil; Dalîl', 'دليل', 'Rehber ', 'Guide', 'Guide'], ['Demiryolu', 'دميريول', 'Demiryolu', 'Railroad', 'Chemin de fer'], ['Deniz Kitabı', 'كتاب بحري', 'Deniz Kitabı', 'Book of the Sea', 'Livre de la Mer '], ['Derya', 'دريا', 'Deniz', 'Sea', 'Mer'], ['Dirâsat ', 'دراسة', 'Bahslar ', 'Studies ', 'Études'], ['Dîvân ', 'ديوان', 'Antoloji', 'Anthology', 'Anthologie '], ['Esmâ-i Bilâd', 'أسماء البلاد', 'Ülkelerin Isimler', 'Names of Countries ', 'Noms des Pays '], ['Fenn', 'فن', 'Bİlim/Bilgi', 'Science/Knowledge', 'Science/Savoir'], ['Fenni', 'فني', 'Bilimsel', 'Scientific/technical', 'Scientifique'], ['Fezleke', 'فذلكه', 'Özet', 'Summary ', 'Resumé'], ['Garâ’ib', 'غرائب', 'Tuhaf, garip şeyler', 'Wonders ', 'Merveilles'], ['Garâ’ib al-Mavcüdât', 'غرائب الموجودات', 'Garip Vücutlar', 'Wonders of Beings ', 'Merveilles des Êtres '], ['Güzergah', 'كذركاهي', 'Güzergah', 'Route', 'Route'], ['Harita hocası', 'خريطه خواجه سي', 'Harita Hocası', 'Map Teacher', 'Enseignant de Carte'], ['Harita; Harîta', 'خريطة', 'Harita', 'Map', 'Map'], ['Haritalar', 'خريطه لر', 'Haritalar', 'Maps', 'Maps'], ['Hey’et', 'هيئة', 'Vücut', 'Body', 'Corps '], ['Hikâyât', 'حكايات', 'Hikayeler', 'Stories', 'Histoires'], ['Hikemî', 'حكمي', 'Felsefi', 'Philosophical', 'Philosophique'], ['Hıtây-nâme', 'خطاي نامه', 'Hitayname', 'Travel Record ', 'Relation de Voyage'], ['Hulâsa', 'خلاصة', 'Özet', 'Summary ', 'Résumé'], ['İklîm-nâme', 'إقليمنامه', 'Bölge Kitabı', 'Book of Region', 'Livre de Region '], ['İktisad', 'إقتصاد', 'Ekonomi', 'Economy', 'Economie'], ['ilm', 'علم', 'ilm', 'Science/Knowledge', 'Science/Savoir'], ['İstatistik', 'استاتيستيق', 'İstatistik', 'Statistics', 'Statisque'], ['Îstatistikî', 'استاتيستيقي', 'İstatistiksel', 'Statistical', 'Statisque'], ['İsti‘lâm', 'استعلام', 'Anket', 'Survey', 'Enquête'], ['Kabartma harita', 'قبارتما خريطه', 'Kabartma harita', 'Relief Map', 'Carte en relief'], ['Kadîm', 'قديم', 'Eski', 'Old', 'Ancien'], ['Kânun', 'قانون', 'Kanun', 'Law', 'Loi'], ['Kitâb; Kitab', 'كتاب', 'Kitap', 'Book ', 'Livre'], ['Kısm', 'قسم', 'Kısım', 'Part', 'Partie'], ['Kıtaât-ı Hamse', 'قطعات خمسه', 'Beş kıta', 'Five Continents', 'Cinq Continents'], ['Kroki', 'قروقي', 'Kroki', 'Sketch', 'Croquis'], ['Küçük Coğrafya', 'جغرافية صغيرة', 'Küçük Coğrafya', 'Small geography', 'Petit Géographie'], ['Küre-i Arz', 'الكرة الأرضية', 'Yerküre', 'Terrestrial globe', 'Globe terrestre'], ['Lâyiha', 'لايحه', 'Tasarı', 'Statement', 'Déclaration'], ['Lügat', 'لغت', 'Sözlük', 'Dictionary', 'Dictionaire'], ['Ma‘rifat', 'معرفة', 'Bilgi', 'Knowlegde ', 'Connaissance '], ['Macmü’at', 'مجموعة', 'Mecmua', 'Collection', 'Collection '], ['Madhal ', 'مدخل', 'Giriş', 'Introduction ', 'Introduction'], ['Malûmât', 'معلومات', 'Haberler/Bilgi', 'News/Information', 'Information'], ['Mamâlik', 'ممالك', 'Memleket/Memleketler', 'Countries/Lands', 'Pays '], ['Manâsik al-Masâlik', 'مناسك المسالك', 'Ritüel', 'Rite', 'Rituel '], ['Manâzil', 'منازل', 'Menziller ', 'Transportations', 'Transport'], ['Manazir', 'مناظر', 'Görünümler', 'Views', 'Vues '], ['Mebâdi', 'مبادئ', 'Mebdeler', 'Principles', 'Principes '], ['Memâlik-i Mahrüsa-ı Şâhâne', 'ممالك محروسهء شاهانه', 'Korunmuş Memleketler (Osmanlı İmparatorluğu)', 'The Well-Protected Domains', '?'], ['Memâlik-i Osmaniye', 'ممالك عثمانية', 'Osmanlı Toprakları', 'Ottoman Lands', 'Terres Ottomanes'], ['Menzilnâme', 'منزلنامه', 'Menzil Kitabı', 'Book of Transportation ', 'Livre de Transport '], ['Merâhil', 'مراحل', 'Aşama ', 'Stages', 'Étapes'], ['Mesafe', 'مسافه', 'Mesafe', 'Distance', 'Distance'], ['Millî', 'ملي', 'Milli', 'National', 'National'], ["Mir'at-ül Coğrafya", 'مرآت جغرافيا', 'Coğrafya aynası', 'The mirror of geography', 'Mirroire de Géographie'], ['Mir’ât', 'مرآت', 'Ayna', 'Mirror', 'Miroir'], ['Mir’ât al-Kâinât', 'مرآت الكائنات', 'Kainat Aynası', 'Mirror of the Universe', "Mirroir de l'Univers"], ['Mücmel', 'مجمل', 'Öz/Kısa/Kısaltılmış', 'Succinct', 'Concis'], ['Mufassal', 'مفصّل', 'Memleketler', 'States', 'États '], ['Mufradat', 'مفردات', 'Ifadeler ', 'Expressions', 'Expréssions '], ['Muhît', 'محيط', 'Çevre', 'Surroundings', 'Alentours'], ['Muhtasar', 'مختصر', 'Kısa/Özet', 'Abridged', 'abrégé'], ['Mukaddime', 'مقدمة', 'Giriş', 'Introduction ', 'Introduction'], ['Mükemmel', 'مكمل', 'Mükemmel', 'Perfect/Complete', 'Parfait/Total'], ['Mülahhas', 'ملخص', 'Özet', 'Summary ', 'Resumé'], ['Münşaât', 'منشآت', 'Inşaatlar', 'Constructions', 'Constructions '], ['Musahabe', 'مصاحبة', 'Konuşma', 'Discussions', 'Debats'], ['Musavver', 'مصور', 'Resimli', 'Illustrated', 'Illustré'], ['Mutâlaât', 'مطالعة', 'Düşünceler', 'Thoughts', 'Pensées'], ['Müzekkire', 'مذكرة', 'Inceleme Yazısı', 'Memoir', 'Mémoire'], ['Nazari', 'نظري', 'Kuramsal', 'theoretical', 'Théorique'], ['Okyanusya', '', 'Okyanusya', 'Oceania', "L'Océanie"], ['Ordu', 'أوردي', 'Ordu', 'Army', 'Armée'], ['Orta', '', 'Orta', 'Middle', 'Intermédiaire'], ['Osmânî', 'عثماني', 'Osmanlı', 'Ottoman', 'Ottomane'], ['Osmaniye', 'عثمانيه', 'Osmanlı', 'Ottoman', 'Ottomane'], ['Ravzat', 'روضة', 'Bahçeler', 'Gardens', 'Jardins'], ['Rehber', 'رهبر', 'Rehber ', 'Guide', 'Guide'], ['Rehnümâ', 'رهنما', 'Kılavuz', 'Guide', 'Guide'], ['Resimli', 'رسملي', 'Resimli', 'Illustrated', 'Illustré'], ['Rihla', 'رحلة', 'Seyahat', 'Travel', 'Voyage'], ['Risale; Risâla', 'رسالة', 'Risale', 'Treatise', 'Traité'], ['Rivâyât', 'روايات', 'Rivayetler', 'Hearsay', 'Ouï-dire'], ['Sefaretnâme; Sefaret-nâme; Sefâretnâme', 'سفارتنامه', 'Elçilik Kitabı', 'Book of Travels, Ambassadorial Report', "Relation de Voyage, Rapport d'ambassadeur"], ['Sefer', 'سفر', 'Sefer', 'Expedition', 'Expédition'], ['Şekilli', 'شكللي', 'Şekilli', 'Illustrated', 'Illustré'], ['Seyahat', 'سياحة/سياحت', 'seyahat', 'Travel', 'Voyage'], ['Seyahatname', 'سياحتنامه', 'Seyahat Kitabı', 'Book of Travels', 'Relation de Voyage'], ['Sira ', 'سيرة', 'Biografi', 'Biography', 'Biographie'], ['Sualli ve Cevaplı', 'سؤاللي وجوابلي', 'Soru ve cevaplı', 'Questions and answers', 'Questions et Réponses'], ['Ta’rif ve Evsafı', 'تعريف وأوصافي', 'Tarif ve Evsafı', 'Description and Characteristics', 'Description et Characteristiques '], ['Tahdit', '', 'Sınırlandırma', 'Delimitation', 'Délimitation'], ['Tahsîl', 'تحصيل', 'Eğitim', 'Education', 'Education'], ['Taksim', 'تقسيم', 'Bölme', 'Partition', 'Partition'], ['Talhîs; Telhıs', 'تلخيص', 'Özet', 'Summary ', 'Sommaire '], ['Tarcamat', '', 'Çeviriler', 'Translations', 'Traduction'], ['Târîfât', 'تعريفات', 'Tariflar', 'Descriptions', 'Descriptions'], ['Tarih ', 'تاريخ', 'Tarih ', 'History', 'Histoire '], ['Tastîh', 'تسطيح', 'Düzleme yansıtma', 'projection (on a plane)', 'projection'], ['Tazkirat', 'تذكرة', 'Inceleme Yazısı', 'Memoir', 'Mémoire'], ['Tedkîkât', 'تدقيقات', 'Tetkikler', 'Survey', 'étude'], ['Tedris', 'تدريس', 'Öğretim', 'Teaching', 'Enseignement'], ['Terceme ', 'ترجمة', 'Tercüme', 'Translation', 'Traduction '], ['Tersim', 'ترسيم', 'Resmini yapma', 'Sketching/Drawing', 'Esquisse (?)'], ['Tıbbî', 'طبّي', 'Tıbbii', 'Medical', 'Médical'], ['Topografya', 'طپوغرافيا', 'Topografya', 'Topography', 'Topographie'], ['Tuhfat', 'تحفة', 'Şaheserler', 'Masterpieces ', "Chef-d'oeuvres"], ['Umûmî', 'عمومي', 'Genel', 'General', 'général'], ['Umûmî Atlas', 'عمومي آطلس', 'Genel atlas', 'General atlas', 'Atlas Général'], ['Usûl', 'أصول', 'Yöntem', 'Method', 'Méthode'], ['Vatanî', 'وطني', 'Vatanla İlgili', 'National', 'National'], ['Vilayet', 'ولايت', 'Vilayet', 'Province', 'Province'], ['Yazısız Harita Defteri', 'يازيسز خريطه دفتري', 'Yazısız Harita Defteri', 'Unlettered/blank Map Notebook', 'Livre de carte Illetrée'], ['Yeni', 'يكي', 'Yeni', 'New', 'Nouveau'], ['Yürüyüş', 'يورييوش ', 'Yürüyüş', 'Walking', 'Marche'], ['Zamân', 'زمان', 'Zaman', 'Time', 'Temps'], ['Ziraat', 'زراعت', 'Ziraat', 'Agriculture', 'Agriculture'], ['Ziyârât', 'زيارات', 'Ziyaretler', 'Sacred Site Visits (Pilgrimage)', 'Voyage/Pélerinage'], ['Zubdat', 'زبدة', 'Özet', 'Summary ', 'Sommaire ']]

      $("#genres").on('change', function (){
          if ($(this).val() == "ottoman"){
               changeLanguage(0);
          } else if ($(this).val() == "arabic"){
              changeLanguage(1);
          } else if ($(this).val() == "modern-turkish"){
              changeLanguage(2);
          } else if ($(this).val() == "english"){
            changeLanguage(3);
          } else if ($(this).val() == "french"){
            changeLanguage(4);
          } else {
            console.log("you done goofed");
          }
        });

       /* columm 8 only has ottoman translation so fix it so it routes to that even if a diff language -- i think this should work but fix undefined */
   function changeLanguage(index){
     $('#genre-menu-here').empty();
      for (var i = 1; i< genres.length; i++){
          document.getElementById("genre-menu-here").innerHTML += `<label class="label-checkbox" id="${genres[i][0]}-8"><input type="checkbox"><span>`+ genres[i][index] + '</span></label>';    
        }
     }

     $(document).ready(function () {
             var table = $('#myTable').DataTable({

                 "columnDefs": [
                  {
                    /* Hiding certain columns */
                      "targets": [0,3,4,11,12,13,14,15,16,17,18,19,20],
                      "visible" : false,
                      "searchable" : true,
                  }
                  ],
               });

          var dict = {};

          /*all category buttons i think */
          $('.label-checkbox').each( function () {
            var dash = $(this).attr('id').indexOf("-");
            $(this).change( () => filterClick(dict, table, parseInt($(this).attr('id').slice(dash+1)), $(this).attr('id').slice(0,dash), '#'+ $(this).attr('id') + ' input:checkbox') )
          });


          $('#reset-filter').click( function (){
              for (var key in dict){
                if (dict.hasOwnProperty(key)){
                  delete dict[key];
                }
              }
              filtAll(dict);
              table.draw();
            })

          $('#reset-search').click( function (){
              table.search('').draw();
            });

          $('tr:not(.headerfooter)').on( 'click', function () {
              var row = table.row($(this));
              if (row.child.isShown()) {
                  row.child.hide();
                  $(this).removeClass('shown');
              } else {
                  if(row.child() && row.child().length){
                    row.child.show();
                  }
                  else {
                    row.child( format(row, table) ).show();
                  }
                  $(this).addClass('shown');
                }

                });

                $("#myTable_filter.dataTables_filter").append($("#categoryFilter"));
                $("#myTable_filter.dataTables_filter").append($("#resets"));
                $("#myTable_filter.dataTables_filter").append($("#turkish-letters"));

                /* Changing input and filter will redraw */
                $("#categoryFilter").on('change', function (){
                  searchByCategory(table);
                  });

                $('input[type="search"]').on('keyup change', function (){
                    searchByCategory(table);
                  });


          });

        function input(letter){
            $('input[type="search"]').val($('input[type="search"]').val() + letter);
            $('input[type="search"]').focus();
            $('input[type="search"]').change();
          }

        function searchByCategory(table){
          $.fn.dataTable.ext.search.push( function (settings, data, dataIndex) {
              var categoryColumn = parseInt( $("#categoryFilter").val() );
              var searchKey = $('input[type="search"]').val();

              /* 'show all' break case - definitely a better way to do this but oh well it works */
              if (categoryColumn == -1){
                var numColumns = $('#myTable').dataTable().fnSettings().aoColumns.length;
                for (let i = 0; i < numColumns; i++){
                  if (data[i].toUpperCase().includes(searchKey.toUpperCase())){
                    return true;
                  }
                }
                return false;
              }
              else if (data[categoryColumn].toUpperCase().includes(searchKey.toUpperCase())){
                return true;
              }
              else{
                return false;
              }
              });
              table.draw();
        }

          function format(row, table) {
              metadata = '';
              /* MAKE THIS SCALABLE ? */
              for (let i = 11; i <= 20; i++){
                metadata += '<div>' + table.column(i).header().innerHTML + ": " + row.data()[i] + '</div>';
              }
              return metadata;
          }

          function filterClick(dict, table, col, keyword, element){
            ($(element).is(':checked')) ? addDict(dict, col, keyword) : removeFromDict(dict, col, keyword);
            filtAll(dict);
            table.draw();
          }


          function addDict(dict, key, val) {
            var subArray;
            if (!(key in dict)){
              subArray = [val];
            }
            else{
              subArray = dict[key];
              subArray.push(val);
            }
            dict[key] = subArray;
          }

          function removeFromDict(dict, key, val){
            dict[key] = dict[key].filter(function (e) { return e!== val});
            if (dict[key].length == 0){
              delete dict[key];
            }
          }

          function filtAll(dict) {
           document.getElementById("test").innerHTML = JSON.stringify(dict);

            $.fn.dataTable.ext.search.push(function (settings, data, dataIndex){
            if (Object.keys(dict).length === 0){
              return true;
            }
            else{
            for (var [key, arrayVals] of Object.entries(dict)){
              var fitsCriteria = false;
              var key = parseInt(`${key}`);
             for (var i in arrayVals){
               if (data[key].toUpperCase().includes(arrayVals[i].toUpperCase())) {
                 fitsCriteria = true;
                 }
             }
             if (!fitsCriteria){
              return false;
              }
            }
            if (fitsCriteria){
              return true;
            }
          }
          });
        }


    </script>


