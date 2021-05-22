<template>
  <div id="info-container">
    <div id="instructions"><p>Scroll below to advance the story!</p></div>
    <div id="info-track">
      <section>
        <div class="info-box" data-step="1">
          <p>
            When it comes to budgetary spending, there is one golden rule: you
            spend more, you get more. This holds true for most budgets,
            including those of our representatives in Congress. Considering that
            our tax dollars are what these budgets consist of, we might want to
            know how much our representatives are spending, and on what.
          </p>
          <p>
            On the other hand, the United States is a purposefully large
            republic with a wide range of cultural differences and a variety of
            needs—so
            <b
              >to what extent does geography factor into our representatives’
              budgetary spending habits?</b
            >
            Let's find out!
          </p>
        </div>
      </section>
      <section>
        <div id="waypoint" class="info-box" data-step="2">
          <p>
            As you can see from how detailed the map to your left is, we’re
            going to be working on a district-level basis. This is because, as
            you’ll shortly see, the top spenders can make a state seem like a
            bigger spender than it actually is.
          </p>
          <p class="table-1"></p>
        </div>
      </section>
      <section @wheel="$emit('stepcatcher', step)">
        <div class="info-box" data-step="3">
          <p>
            This map shows the total amount that congressional representatives
            have reported spending so far in 2020.
          </p>
          <p>
            You can click and drag the map on the left, or zoom in to look at
            specific districts. This particular map reveals that, while all
            representatives spend a lot, the highest spenders represent
            districts that are from large states, or districts notable for
            containing big cities. Below you’ll find a table listing the top
            five spenders. Click on any district on the map to see information about the spender!
          </p>
           <p style="font-size:14px;">You may note that a representative on this table is from Puerto Rico, which is not a state; the House has delegate representatives from our territories, who get budgets for their offices.</p>
           <p><b>Top 5 Overall Spenders</b></p>
          <p class="table-2">
            <table class="table-dist">
              <thead>
                <tr>
                  <th style="font-size: 16px;">Representative</th>
                  <th style="font-size: 16px;">Party</th>
                  <th style="font-size: 16px;">State</th>
                  <th style="font-size: 16px;">Geoid</th>
                  <th style="font-size: 16px;">Amount</th>
                </tr>
              </thead>
              <tbody>
                <tr style="background-color: rgb(73, 169, 171); color: rgb(238, 238, 238);">
                  <td style="font-size: 14px; padding: 0.7em;">Jenniffer González-Colón</td>
                  <td style="font-size: 14px; padding: 0.7em;">Republican</td>
                  <td style="font-size: 14px; padding: 0.7em;">PR</td>
                  <td style="font-size: 14px; padding: 0.7em;">7298</td>
                  <td style="font-size: 14px; padding: 0.7em;">1,712,723</td>
                  </tr>
                  <tr style="background-color: rgb(108, 180, 180); color: rgb(238, 238, 238);">
                    <td style="font-size: 14px; padding: 0.7em;">Carolyn B. Maloney</td>
                    <td style="font-size: 14px; padding: 0.7em;">Democrat</td>
                    <td style="font-size: 14px; padding: 0.7em;">NY</td>
                    <td style="font-size: 14px; padding: 0.7em;">3612</td>
                    <td style="font-size: 14px; padding: 0.7em;">1,546,331</td>
                    </tr>
                    <tr style="background-color: rgb(111, 181, 181); color: rgb(238, 238, 238);">
                      <td style="font-size: 14px; padding: 0.7em;">Jerrold Nadler</td>
                      <td style="font-size: 14px; padding: 0.7em;">Democrat</td>
                      <td style="font-size: 14px; padding: 0.7em;">NY</td>
                      <td style="font-size: 14px; padding: 0.7em;">3610</td>
                      <td style="font-size: 14px; padding: 0.7em;">1,536,029</td>
                      </tr>
                  <tr style="background-color: rgb(112, 181, 181); color: rgb(238, 238, 238);">
                    <td style="font-size: 14px; padding: 0.7em;">Suzanne Bonamici</td>
                    <td style="font-size: 14px; padding: 0.7em;">Democrat</td>
                    <td style="font-size: 14px; padding: 0.7em;">OR</td>
                    <td style="font-size: 14px; padding: 0.7em;">4101</td>
                    <td style="font-size: 14px; padding: 0.7em;">1,529,780</td></tr>
                    <tr style="background-color: rgb(112, 181, 181); color: rgb(238, 238, 238);">
                      <td style="font-size: 14px; padding: 0.7em;">Elissa Slotkin</td>
                      <td style="font-size: 14px; padding: 0.7em;">Democrat</td>
                      <td style="font-size: 14px; padding: 0.7em;">MI</td>
                      <td style="font-size: 14px; padding: 0.7em;">2608</td>
                      <td style="font-size: 14px; padding: 0.7em;">1,529,557</td></tr>
                      </tbody>
                      </table>
              </p>
        </div>
      </section>
      <section>
        <div class="info-box" data-step="4">
          <p>
            Why are these representatives reporting so much spending? What do
            representatives from California, Texas, and New York have in common?
            Let’s drill down into some categories and see what’s going on.
          </p>
        </div>
      </section>
      <section @wheel="$emit('stepcatcher', step)">
        <div class="info-box" data-step="5">
          <p>
            The category that representatives spend the most on is personnel
            compensation, which makes sense given that most salaries are in
            range of 30,000 and above. However, because representatives are
            given a specific amount to spend based on population of their
            district (per the
            <a
              href="https://www.house.gov/the-house-explained/open-government/statement-of-disbursements/glossary-of-terms"
              >glossary of spending from the House of Representatives</a
            >), this map doesn’t hold much useful information. Below is a table
            showing the top five spenders on personnel compensation.
          </p>
         <p><b>Top 5 Personnel Compensation Spenders</b></p>
          <p class="table-3"><table class="table-dist"><thead><tr><th style="font-size: 16px;">Representative</th><th style="font-size: 16px;">Party</th><th style="font-size: 16px;">State</th><th style="font-size: 16px;">Geoid</th><th style="font-size: 16px;">Amount</th></tr></thead><tbody><tr style="background-color: rgb(73, 169, 171); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Theodore E. Deutch</td><td style="font-size: 14px; padding: 0.7em;">Democrat</td><td style="font-size: 14px; padding: 0.7em;">FL</td><td style="font-size: 14px; padding: 0.7em;">1222</td><td style="font-size: 14px; padding: 0.7em;">1,312,348</td></tr><tr style="background-color: rgb(78, 170, 172); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Denny Heck</td><td style="font-size: 14px; padding: 0.7em;">Democrat</td><td style="font-size: 14px; padding: 0.7em;">WA</td><td style="font-size: 14px; padding: 0.7em;">5310</td><td style="font-size: 14px; padding: 0.7em;">1,306,816</td></tr><tr style="background-color: rgb(90, 174, 175); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Martha Roby</td><td style="font-size: 14px; padding: 0.7em;">Republican</td><td style="font-size: 14px; padding: 0.7em;">AL</td><td style="font-size: 14px; padding: 0.7em;">0102</td><td style="font-size: 14px; padding: 0.7em;">1,292,470</td></tr><tr style="background-color: rgb(99, 177, 178); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">John Shimkus</td><td style="font-size: 14px; padding: 0.7em;">Republican</td><td style="font-size: 14px; padding: 0.7em;">IL</td><td style="font-size: 14px; padding: 0.7em;">1715</td><td style="font-size: 14px; padding: 0.7em;">1,282,744</td></tr><tr style="background-color: rgb(112, 181, 181); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Danny K. Davis</td><td style="font-size: 14px; padding: 0.7em;">Democrat</td><td style="font-size: 14px; padding: 0.7em;">IL</td><td style="font-size: 14px; padding: 0.7em;">1707</td><td style="font-size: 14px; padding: 0.7em;">1,267,389</td></tr></tbody></table></p>
        </div>
      </section>
      <section @wheel="$emit('stepcatcher', step)">
        <div class="info-box" data-step="6">
          <p>
            Those representatives who are the highest spenders in terms of rent,
            communications, and utilities are from tiny districts near highly
            populated cities—you can see small brightly colored “hot spots”
            around those cities in places like California and Texas. Remember that you can click on a
            district on the map that you’re interested in to see more
            information about the representative and the amount spent!
          </p>
          <p><b>Top 5 Spenders<br>Rent, Communications, & Utilities</b></p>
          <p class="table-4"><table class="table-dist"><thead><tr><th style="font-size: 16px;">Representative</th><th style="font-size: 16px;">Party</th><th style="font-size: 16px;">State</th><th style="font-size: 16px;">Geoid</th><th style="font-size: 16px;">Amount</th></tr></thead><tbody><tr style="background-color: rgb(73, 169, 171); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Gregory W. Meeks</td><td style="font-size: 14px; padding: 0.7em;">Democrat</td><td style="font-size: 14px; padding: 0.7em;">NY</td><td style="font-size: 14px; padding: 0.7em;">3605</td><td style="font-size: 14px; padding: 0.7em;">294,504</td></tr><tr style="background-color: rgb(96, 176, 177); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Hakeem S. Jeffries</td><td style="font-size: 14px; padding: 0.7em;">Democrat</td><td style="font-size: 14px; padding: 0.7em;">NY</td><td style="font-size: 14px; padding: 0.7em;">3608</td><td style="font-size: 14px; padding: 0.7em;">247,364</td></tr><tr style="background-color: rgb(99, 177, 178); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Nancy Pelosi</td><td style="font-size: 14px; padding: 0.7em;">Democrat</td><td style="font-size: 14px; padding: 0.7em;">CA</td><td style="font-size: 14px; padding: 0.7em;">0612</td><td style="font-size: 14px; padding: 0.7em;">242,724</td></tr><tr style="background-color: rgb(103, 178, 179); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Anna G. Eshoo</td><td style="font-size: 14px; padding: 0.7em;">Democrat</td><td style="font-size: 14px; padding: 0.7em;">CA</td><td style="font-size: 14px; padding: 0.7em;">0618</td><td style="font-size: 14px; padding: 0.7em;">234,570</td></tr><tr style="background-color: rgb(112, 181, 181); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Eddie Bernice Johnson</td><td style="font-size: 14px; padding: 0.7em;">Democrat</td><td style="font-size: 14px; padding: 0.7em;">TX</td><td style="font-size: 14px; padding: 0.7em;">4830</td><td style="font-size: 14px; padding: 0.7em;">215,494</td></tr></tbody></table></p>
        </div>
      </section>
      <section @wheel="$emit('stepcatcher', step)">
        <div class="info-box" data-step="7">
          <p>
            Printing is the next highest category in terms of spending, and it’s
            a bit of a mixed bag. According to the House of Representatives’
            glossary of terms, printing can include “newsletters, postal patron
            mailings, mass mailings, notices of town hall meetings or notices of
            personal appearance of the Member at an official event,
            administrative papers (casework tracking forms, personnel record
            forms, etc.), legislative papers (bills, drafts, summaries,
            amendments, etc.), business cards for Members and their employees,
            stuffing, sealing and associated expenses relating to printing and
            sending official mail,” among other things. The highest spenders in
            this category are, strangely enough, representing some unexpected
            locations.
          </p>
          <p><b>Top 5 Printing Spenders</b></p>
          <p class="table-5"><table class="table-dist"><thead><tr><th style="font-size: 16px;">Representative</th><th style="font-size: 16px;">Party</th><th style="font-size: 16px;">State</th><th style="font-size: 16px;">Geoid</th><th style="font-size: 16px;">Amount</th></tr></thead><tbody><tr style="background-color: rgb(73, 169, 171); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Ross Spano</td><td style="font-size: 14px; padding: 0.7em;">Republican</td><td style="font-size: 14px; padding: 0.7em;">FL</td><td style="font-size: 14px; padding: 0.7em;">1215</td><td style="font-size: 14px; padding: 0.7em;">287,548</td></tr><tr style="background-color: rgb(74, 169, 171); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Dan Bishop</td><td style="font-size: 14px; padding: 0.7em;">Republican</td><td style="font-size: 14px; padding: 0.7em;">NC</td><td style="font-size: 14px; padding: 0.7em;">3709</td><td style="font-size: 14px; padding: 0.7em;">286,103</td></tr><tr style="background-color: rgb(81, 171, 173); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Jim Hagedorn</td><td style="font-size: 14px; padding: 0.7em;">Republican</td><td style="font-size: 14px; padding: 0.7em;">MN</td><td style="font-size: 14px; padding: 0.7em;">2701</td><td style="font-size: 14px; padding: 0.7em;">270,375</td></tr><tr style="background-color: rgb(108, 180, 180); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Katie Porter</td><td style="font-size: 14px; padding: 0.7em;">Democrat</td><td style="font-size: 14px; padding: 0.7em;">CA</td><td style="font-size: 14px; padding: 0.7em;">0645</td><td style="font-size: 14px; padding: 0.7em;">209,997</td></tr><tr style="background-color: rgb(112, 181, 181); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Gerald E. Connolly</td><td style="font-size: 14px; padding: 0.7em;">Democrat</td><td style="font-size: 14px; padding: 0.7em;">VA</td><td style="font-size: 14px; padding: 0.7em;">5111</td><td style="font-size: 14px; padding: 0.7em;">202,329</td></tr></tbody></table></p>
        </div>
      </section>
      <section @wheel="$emit('stepcatcher', step)">
        <div class="info-box" data-step="8">
          <p>
            “Other Services” sounds like a very nebulous category, and it can
            be—the House of Representatives defines this category as
            “obligations for contractual services including training.”
            Basically, whenever representatives reimburse tuition for their
            staff or hire a firm to provide services for them, they mark the
            spending down in this category. The highest spenders in this
            category are in populous cities regardless of party—zoom in on NYC,
            San Jose, and Houston to check out the highlights!
          </p>
          <p><b>Top 5 "Other Services" Spenders</b></p>
          <p class="table-6"><table class="table-dist"><thead><tr><th style="font-size: 16px;">Representative</th><th style="font-size: 16px;">Party</th><th style="font-size: 16px;">State</th><th style="font-size: 16px;">Geoid</th><th style="font-size: 16px;">Amount</th></tr></thead><tbody><tr style="background-color: rgb(73, 169, 171); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Roger Williams</td><td style="font-size: 14px; padding: 0.7em;">Republican</td><td style="font-size: 14px; padding: 0.7em;">TX</td><td style="font-size: 14px; padding: 0.7em;">4825</td><td style="font-size: 14px; padding: 0.7em;">117,046</td></tr><tr style="background-color: rgb(85, 173, 174); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Bill Pascrell, Jr.</td><td style="font-size: 14px; padding: 0.7em;">Democrat</td><td style="font-size: 14px; padding: 0.7em;">NJ</td><td style="font-size: 14px; padding: 0.7em;">3409</td><td style="font-size: 14px; padding: 0.7em;">104,473</td></tr><tr style="background-color: rgb(90, 174, 175); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Sheila Jackson Lee</td><td style="font-size: 14px; padding: 0.7em;">Democrat</td><td style="font-size: 14px; padding: 0.7em;">TX</td><td style="font-size: 14px; padding: 0.7em;">4818</td><td style="font-size: 14px; padding: 0.7em;">99,142</td></tr><tr style="background-color: rgb(108, 180, 180); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Harley Rouda</td><td style="font-size: 14px; padding: 0.7em;">Democrat</td><td style="font-size: 14px; padding: 0.7em;">CA</td><td style="font-size: 14px; padding: 0.7em;">0648</td><td style="font-size: 14px; padding: 0.7em;">79,783</td></tr><tr style="background-color: rgb(112, 181, 181); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Alexandria Ocasio-Cortez</td><td style="font-size: 14px; padding: 0.7em;">Democrat</td><td style="font-size: 14px; padding: 0.7em;">NY</td><td style="font-size: 14px; padding: 0.7em;">3614</td><td style="font-size: 14px; padding: 0.7em;">75,802</td></tr></tbody></table></p>
        </div>
      </section>
      <section @wheel="$emit('stepcatcher', step)">
        <div class="info-box" data-step="9">
          <p>
            Franked mail is a fascinating category. Defined by the House as
            reimbursable “postage expenses of specific pieces of mail sent out
            by Members,” franking privileges tend to be how incumbents can get a
            leg up on their opponents when it comes time for re-election. While
            you can’t get campaign materials reimbursed, franking privileges
            give incumbents name recognition. Little wonder, then, that the
            highest spenders in this category tend to be Republicans in
            geographically small city districts—an indication that they’re
            trying to hang on tight to those districts.
          </p>
          <p><b>Top 5 Franked Mail Spenders</b></p>
          <p class="table-7"><table class="table-dist"><thead><tr><th style="font-size: 16px;">Representative</th><th style="font-size: 16px;">Party</th><th style="font-size: 16px;">State</th><th style="font-size: 16px;">Geoid</th><th style="font-size: 16px;">Amount</th></tr></thead><tbody><tr style="background-color: rgb(73, 169, 171); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Ron Wright</td><td style="font-size: 14px; padding: 0.7em;">Republican</td><td style="font-size: 14px; padding: 0.7em;">TX</td><td style="font-size: 14px; padding: 0.7em;">4806</td><td style="font-size: 14px; padding: 0.7em;">268,254</td></tr><tr style="background-color: rgb(95, 176, 177); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Devin Nunes</td><td style="font-size: 14px; padding: 0.7em;">Republican</td><td style="font-size: 14px; padding: 0.7em;">CA</td><td style="font-size: 14px; padding: 0.7em;">0622</td><td style="font-size: 14px; padding: 0.7em;">199,234</td></tr><tr style="background-color: rgb(109, 180, 180); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">John Garamendi</td><td style="font-size: 14px; padding: 0.7em;">Democrat</td><td style="font-size: 14px; padding: 0.7em;">CA</td><td style="font-size: 14px; padding: 0.7em;">0603</td><td style="font-size: 14px; padding: 0.7em;">155,702</td></tr><tr style="background-color: rgb(110, 180, 181); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Dan Bishop</td><td style="font-size: 14px; padding: 0.7em;">Republican</td><td style="font-size: 14px; padding: 0.7em;">NC</td><td style="font-size: 14px; padding: 0.7em;">3709</td><td style="font-size: 14px; padding: 0.7em;">153,614</td></tr><tr style="background-color: rgb(112, 181, 181); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Alexander Mooney</td><td style="font-size: 14px; padding: 0.7em;">Republican</td><td style="font-size: 14px; padding: 0.7em;">WV</td><td style="font-size: 14px; padding: 0.7em;">5402</td><td style="font-size: 14px; padding: 0.7em;">147,625</td></tr></tbody></table></p>
        </div>
      </section>
      <section @wheel="$emit('stepcatcher', step)">
        <div class="info-box" data-step="10">
          <p>
            If you’ve ever worked in an office, you know what spending on
            supplies entails. It’s your standard trip to Staples to get
            highlighters, binder clips, and anything else you might need in the
            normal course of business. The map might seem surprising, but this
            may be more of an indication that most of those representatives
            <a
              href="https://www.propublica.org/article/update-on-house-disbursements-a-few-notes-on-how-to-use-the-data"
              >haven’t gotten their receipts in on time for reporting!</a
            >
          </p>
          <p><b>Top 5 Supplies Spenders</b></p>
          <p class="table-8"><table class="table-dist"><thead><tr><th style="font-size: 16px;">Representative</th><th style="font-size: 16px;">Party</th><th style="font-size: 16px;">State</th><th style="font-size: 16px;">Geoid</th><th style="font-size: 16px;">Amount</th></tr></thead><tbody><tr style="background-color: rgb(73, 169, 171); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Jenniffer González-Colón</td><td style="font-size: 14px; padding: 0.7em;">Republican</td><td style="font-size: 14px; padding: 0.7em;">PR</td><td style="font-size: 14px; padding: 0.7em;">7298</td><td style="font-size: 14px; padding: 0.7em;">176,190</td></tr><tr style="background-color: rgb(109, 180, 180); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Joe Courtney</td><td style="font-size: 14px; padding: 0.7em;">Democrat</td><td style="font-size: 14px; padding: 0.7em;">CT</td><td style="font-size: 14px; padding: 0.7em;">0902</td><td style="font-size: 14px; padding: 0.7em;">78,673</td></tr><tr style="background-color: rgb(111, 181, 181); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Greg Stanton</td><td style="font-size: 14px; padding: 0.7em;">Democrat</td><td style="font-size: 14px; padding: 0.7em;">AZ</td><td style="font-size: 14px; padding: 0.7em;">0409</td><td style="font-size: 14px; padding: 0.7em;">75,103</td></tr><tr style="background-color: rgb(111, 181, 181); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Diana DeGette</td><td style="font-size: 14px; padding: 0.7em;">Democrat</td><td style="font-size: 14px; padding: 0.7em;">CO</td><td style="font-size: 14px; padding: 0.7em;">0801</td><td style="font-size: 14px; padding: 0.7em;">73,650</td></tr><tr style="background-color: rgb(112, 181, 181); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Scott DesJarlais</td><td style="font-size: 14px; padding: 0.7em;">Republican</td><td style="font-size: 14px; padding: 0.7em;">TN</td><td style="font-size: 14px; padding: 0.7em;">4704</td><td style="font-size: 14px; padding: 0.7em;">71,854</td></tr></tbody></table></p>
        </div>
      </section>
      <section @wheel="$emit('stepcatcher', step)">
        <div class="info-box" data-step="11">
          <p>
            Something that might not be apparent at first glance when
            considering spending on travel is that when representatives get
            reimbursed for travel expenses, this also includes meals! Our
            highest spenders here tend to be representing large districts in big
            states (e.g. KS, AZ, TX). This makes some sense when considering
            that representatives can sometimes go back to their districts to
            hear constituents’ concerns.
          </p>
          <p><b>Top 5 Travel Spenders</b></p>
          <p class="table-9"><table class="table-dist"><thead><tr><th style="font-size: 16px;">Representative</th><th style="font-size: 16px;">Party</th><th style="font-size: 16px;">State</th><th style="font-size: 16px;">Geoid</th><th style="font-size: 16px;">Amount</th></tr></thead><tbody><tr style="background-color: rgb(73, 169, 171); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Roger Marshall</td><td style="font-size: 14px; padding: 0.7em;">Republican</td><td style="font-size: 14px; padding: 0.7em;">KS</td><td style="font-size: 14px; padding: 0.7em;">2001</td><td style="font-size: 14px; padding: 0.7em;">133,775</td></tr><tr style="background-color: rgb(89, 174, 175); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Paul A. Gosar</td><td style="font-size: 14px; padding: 0.7em;">Republican</td><td style="font-size: 14px; padding: 0.7em;">AZ</td><td style="font-size: 14px; padding: 0.7em;">0404</td><td style="font-size: 14px; padding: 0.7em;">116,312</td></tr><tr style="background-color: rgb(98, 177, 177); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Roger Williams</td><td style="font-size: 14px; padding: 0.7em;">Republican</td><td style="font-size: 14px; padding: 0.7em;">TX</td><td style="font-size: 14px; padding: 0.7em;">4825</td><td style="font-size: 14px; padding: 0.7em;">105,476</td></tr><tr style="background-color: rgb(102, 178, 179); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Lance Gooden</td><td style="font-size: 14px; padding: 0.7em;">Republican</td><td style="font-size: 14px; padding: 0.7em;">TX</td><td style="font-size: 14px; padding: 0.7em;">4805</td><td style="font-size: 14px; padding: 0.7em;">100,766</td></tr><tr style="background-color: rgb(112, 181, 181); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Stacey E. Plaskett</td><td style="font-size: 14px; padding: 0.7em;">Democrat</td><td style="font-size: 14px; padding: 0.7em;">VI</td><td style="font-size: 14px; padding: 0.7em;">7898</td><td style="font-size: 14px; padding: 0.7em;">90,065</td></tr></tbody></table></p>
        </div>
      </section>
      <section @wheel="$emit('stepcatcher', step)">
        <div class="info-box" data-step="12">
          <p>
            Equipment is a fairly standard category—it describes spending on
            things like computers and hardware, items that the representative
            and their staff can use for a while. More spending in this category
            tends to be done by representatives from smaller districts
            (indicating more populous cities).
          </p>
          <p><b>Top 5 Equipment Spenders</b></p>
          <p class="table-10"><table class="table-dist"><thead><tr><th style="font-size: 16px;">Representative</th><th style="font-size: 16px;">Party</th><th style="font-size: 16px;">State</th><th style="font-size: 16px;">Geoid</th><th style="font-size: 16px;">Amount</th></tr></thead><tbody><tr style="background-color: rgb(73, 169, 171); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Jerrold Nadler</td><td style="font-size: 14px; padding: 0.7em;">Democrat</td><td style="font-size: 14px; padding: 0.7em;">NY</td><td style="font-size: 14px; padding: 0.7em;">3610</td><td style="font-size: 14px; padding: 0.7em;">112,776</td></tr><tr style="background-color: rgb(82, 172, 173); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Michael C. Burgess</td><td style="font-size: 14px; padding: 0.7em;">Republican</td><td style="font-size: 14px; padding: 0.7em;">TX</td><td style="font-size: 14px; padding: 0.7em;">4826</td><td style="font-size: 14px; padding: 0.7em;">101,034</td></tr><tr style="background-color: rgb(101, 178, 178); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">James P. McGovern</td><td style="font-size: 14px; padding: 0.7em;">Democrat</td><td style="font-size: 14px; padding: 0.7em;">MA</td><td style="font-size: 14px; padding: 0.7em;">2502</td><td style="font-size: 14px; padding: 0.7em;">76,350</td></tr><tr style="background-color: rgb(105, 179, 179); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Jesús G. "Chuy" García</td><td style="font-size: 14px; padding: 0.7em;">Democrat</td><td style="font-size: 14px; padding: 0.7em;">IL</td><td style="font-size: 14px; padding: 0.7em;">1704</td><td style="font-size: 14px; padding: 0.7em;">71,731</td></tr><tr style="background-color: rgb(112, 181, 181); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Steven Horsford</td><td style="font-size: 14px; padding: 0.7em;">Democrat</td><td style="font-size: 14px; padding: 0.7em;">NV</td><td style="font-size: 14px; padding: 0.7em;">3204</td><td style="font-size: 14px; padding: 0.7em;">62,744</td></tr></tbody></table></p>
        </div>
      </section>
      <section @wheel="$emit('stepcatcher', step)">
        <div class="info-box" data-step="13">
          <p>
            "Transportation of Things" is the final category, and it’s
            incredibly sparse. Either representatives don’t tend to get their
            receipts to the clerk for this category, or they just don’t spend
            enough on transporting items—this is to the extent that the House
            doesn’t have a definition of what this category entails! What data
            we <i>do</i> have on this, however, shows that this kind of spending
            has not been done or reported in the Northwest in 2020.
          </p>
          <p><b>Top 5 Transportation of Things Spenders</b></p>
          <p class="table-11"><table class="table-dist"><thead><tr><th style="font-size: 16px;">Representative</th><th style="font-size: 16px;">Party</th><th style="font-size: 16px;">State</th><th style="font-size: 16px;">Geoid</th><th style="font-size: 16px;">Amount</th></tr></thead><tbody><tr style="background-color: rgb(73, 169, 171); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Ami Bera</td><td style="font-size: 14px; padding: 0.7em;">Democrat</td><td style="font-size: 14px; padding: 0.7em;">CA</td><td style="font-size: 14px; padding: 0.7em;">0607</td><td style="font-size: 14px; padding: 0.7em;">2,900</td></tr><tr style="background-color: rgb(109, 180, 180); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Don Bacon</td><td style="font-size: 14px; padding: 0.7em;">Republican</td><td style="font-size: 14px; padding: 0.7em;">NE</td><td style="font-size: 14px; padding: 0.7em;">3102</td><td style="font-size: 14px; padding: 0.7em;">560</td></tr><tr style="background-color: rgb(110, 180, 181); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">James E. Clyburn</td><td style="font-size: 14px; padding: 0.7em;">Democrat</td><td style="font-size: 14px; padding: 0.7em;">SC</td><td style="font-size: 14px; padding: 0.7em;">4506</td><td style="font-size: 14px; padding: 0.7em;">464</td></tr><tr style="background-color: rgb(112, 181, 181); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">John P. Sarbanes</td><td style="font-size: 14px; padding: 0.7em;">Democrat</td><td style="font-size: 14px; padding: 0.7em;">MD</td><td style="font-size: 14px; padding: 0.7em;">2403</td><td style="font-size: 14px; padding: 0.7em;">350</td></tr><tr style="background-color: rgb(112, 181, 181); color: rgb(238, 238, 238);"><td style="font-size: 14px; padding: 0.7em;">Robert J. Wittman</td><td style="font-size: 14px; padding: 0.7em;">Republican</td><td style="font-size: 14px; padding: 0.7em;">VA</td><td style="font-size: 14px; padding: 0.7em;">5101</td><td style="font-size: 14px; padding: 0.7em;">348</td></tr></tbody></table></p>
        </div>
      </section>
      <section>
        <div class="info-box" data-step="14">
          <p>
            We’ve seen that geography can play an incredibly informative role
            when it comes to representative spending, depending on what they’re
            spending their budgets on. Though the data isn’t perfect, the
            general trend has been that representatives who spend more tend to
            be representing either very large districts or tiny districts that
            slice up populous cities.
          </p>
          <p>
            Categorically, we’ve also seen that geography tends to influence how
            much a representative will spend in the course of engaging with
            their constituents. Whether it’s purchasing hardware for the
            representative’s office so they can communicate with constituents
            hundreds of miles away or buying plane tickets to get to California
            from Washington, DC, there is definitely an impact from geography in
            certain types of spending.
          </p>
          <p>
            As a bit of a parting note, bear in mind that per ProPublica’s
            investigation into the data, house members are allowed to continue
            to report disbursements up to three years after they were made, so
            it’s entirely likely that this isn’t the full extent of the
            data—it’s just everything the representatives in 2020 decided to
            report so far!
          </p>
        </div>
      </section>
      <section>
        <div class="info-box" data-step="15">
          <p>
            To find out more about the 116th Congress and representative
            spending, you can visit
            <a
              href="https://www.house.gov/the-house-explained/open-government/statement-of-disbursements"
              >the official House Disbursements page</a
            >
            and inspect the original PDFs for this year.
          </p>

          <p>
            You can also visit
            <a href="https://projects.propublica.org/represent/expenditures"
              >ProPublica</a
            >
            to read more about how the data was initially scraped and processed.
          </p>

          <p>
            The data documentation and white paper for this project are in the
            header and link to this site’s GitHub repository, where you can
            check out the code for this project as well.
          </p>
        </div>
      </section>
    </div>
  </div>
</template>
<script>
// import * as d3 from "d3";
import "intersection-observer";
import scrollama from "scrollama";
const scroller = scrollama();

export default {
  name: "Info",
  props: ["maindata", "categories", "arrayComputation"],
  emits: ["stepcatcher"],
  data() {
    return {
      step: null,
      columns: ["Representative", "Party", "State", "Geoid", "Amount"],
      tabledata: [],
      classes: [],
      localdata: [],
    };
  },
  methods: {
    scroll: function () {
      console.log(this);
      scroller
        .setup({
          step: "#info-track section .info-box",
          debug: true,
          offset: 0.5,
        })
        .onStepEnter((response) => {
          this.step = response.index;
          console.log(this.step);
        });
    },
  },
  mounted() {
    this.scroll();
  },
};
</script>
<style scoped>
#info-track {
  background-color: rgba(255, 255, 255, 0.38);
  scroll-behavior: smooth;
  overflow-y: scroll;
  scrollbar-width: none;
  height: 88vh;
  height: fit-content;
}

::-webkit-scrollbar {
  display: none;
}
.info-box {
  margin: 2vw;
  background-color: #1b2a36;
  padding: 3vw;
  border-radius: 28px;
  color: #fffbe6;
}

section {
  min-height: 100vh;
  padding: 10vw 5vh;
  text-align: center;
  display: flex;
  align-items: center;
  justify-content: center;
  box-sizing: border-box;
}
#instructions {
  background-color: #28c5d1;
  height: 8vh;
  position: fixed;
  width: 40%;
  /* margin: auto; */
  display: grid;
}
#instructions p {
  color: #1b2a36;
  z-index: 999;
  position: fixed;
  text-align: center;
  /* margin: auto; */
  justify-self: center;
}
a {
  color: #28c5d1;
}
</style>
