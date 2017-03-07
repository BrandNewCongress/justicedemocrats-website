Used to identify corresponding article at a glance.

Archive
```
<div class="fontSecondary" id="volunteerSkills">
    <div class="description">
        <p class="pullout">Tell us all about yourself so we can get you plugged into the best teams.</p>
        <p>This movement won&rsquo;t be possible without thousands of volunteers helping at every level of organization. Join now to make a difference.</p>
        <hr>
    </div>
    <form class="positionAnchor" id="VolunteerForm" name="Volunteer" ng-class="status" ng-cloak="" ng-cloak-reveal="" ng-controller="CustomApi" ng-sanitize="true" ng-submit="send('Volunteer')" options='{"controller":"/volunteers", "scrollTo":"#VolunteerForm", "scrollToOffset":-100, "response": {"success": "Thank you for submitting information about yourself! We will review and get back to you ASAP."},  "dynamicOptions": {"availability":{"available-0-5":"0-5","available-5-10":"5-10","available-10-20":"10-20","available-20-30":"20-30","available-30":"30+"},"skills":{"skill-programming":"Web Development","skill-web-design":"Web Design","skill-graphic-design":"Graphic Design","skill-video":"Video Production","skill-writing":"Writing/Marketing","skill-press":"Press Connections","skill-nationbuilder":"Nationbuilder Administration","skill-data-entry":"Data Entry","skill-call":"Call Supporters","skill-helpdesk":"Answer Helpdesk Emails","skill-sharing":"Share Social","skill-printing":"Provide Printing Services","skill-travel":"Manage and Book Travel","skill-hr":"Operations and HR","skill-legal":"Legal","skill-manage-communities":"Manage Online Communities","skill-supporter-housing":"Can House Supporters","skill-event-host":"Can Host Events","skill-venue":"Have Access to Free or Low-Cost Venues"}} }'>
        <input type="hidden" name="utmSource" ng-model="model.data.utmSource">
        <input type="hidden" name="utmMedium" ng-model="model.data.utmMedium">
        <input type="hidden" name="utmCampaign" ng-model="model.data.utmCampaign">

        <p class="message" ng-show="response.length" ng-bind-html="response"></p>
        <div class="reset" ng-show="status == 'success'">
            <md-button class="btn" ng-click="reset('Volunteer')">Submit Another</md-button>
        </div>
        <div ng-class="{sending: status === 'sending'}" ng-show="status !== 'success'">
            <div layout="row" layout-wrap="">
                <div flex="100" flex-gt-sm="40">
                    <div class="whiteframePadding" md-whiteframe="2">
                        <h2>About You</h2>
                        <div layout="column">
                            <md-input-container>
                                <label class="noFloat" md-no-float="">Your Name</label>
                                <input name="volunteerName" type="text" ng-model="model.data.volunteerName" placeholder="" required="">
                                <div ng-messages="Volunteer.volunteerName.$error" role="alert">
                                    <div ng-message-exp="['required']">Please enter a name.</div>
                                </div>
                            </md-input-container>
                            <md-input-container>
                                <label class="noFloat" md-no-float="">Your Email</label>
                                <input name="volunteerEmail" type="email" ng-pattern="options.pattern.email" ng-model="model.data.volunteerEmail" placeholder="" required="">
                                <div ng-messages="Volunteer.volunteerEmail.$error" role="alert">
                                    <div ng-message-exp="['required', 'pattern']">Please enter a valid email.</div>
                                </div>
                            </md-input-container>
                            <md-input-container>
                                <label class="noFloat" md-no-float="">Your Phone</label>
                                <input name="volunteerPhone" type="tel" ng-model="model.data.volunteerPhone" placeholder="" required="">
                                <div ng-messages="Volunteer.volunteerPhone.$error" role="alert">
                                    <div ng-message-exp="['required']">Please enter a valid phone.</div>
                                </div>
                            </md-input-container>
                            <md-input-container>
                                <label class="noFloat" md-no-float="">Your Address</label>
                                <textarea name="volunteerAddress" ng-model="model.data.volunteerAddress" placeholder="" rows="2" required=""></textarea>
                                <div ng-messages="Volunteer.volunteerAddress.$error" role="alert">
                                    <div ng-message-exp="['required']">Please enter an address.</div>
                                </div>
                            </md-input-container>
                            <md-input-container>
                                <label class="noFloat" md-no-float="">Your City</label>
                                <input name="volunteerCity" ng-model="model.data.volunteerCity" placeholder="" required="">
                                <div ng-messages="Volunteer.volunteerCity.$error" role="alert">
                                    <div ng-message-exp="['required']">Please enter a city.</div>
                                </div>
                            </md-input-container>
                            <md-input-container class="md-input-has-placeholder">
                                <md-select-label class="noFloat" md-no-float="">Your State <span class="required">*</span></md-select-label>
                                <md-select aria-label="Your State" md-no-asterisk="" name="volunteerState" ng-model="model.data.volunteerState" required="true">
                                    <md-option ng-repeat="state in states" ng-value="state.value"> {{ state.text }} </md-option>
                                </md-select>
                                <div ng-messages="Volunteer.volunteerState.$error" role="alert">
                                    <div ng-message-exp="['required']">Please a select a state.</div>
                                </div>
                                <div class="md-errors-spacer"></div>
                            </md-input-container>
                            <md-input-container>
                                <label class="noFloat" md-no-float="">Your Zip</label>
                                <input name="volunteerZip" ng-model="model.data.volunteerZip" placeholder="" required="">
                                <div ng-messages="Volunteer.volunteerZip.$error" role="alert">
                                    <div ng-message-exp="['required']">Please enter a Zip.</div>
                                </div>
                            </md-input-container>
                            <md-input-container>
                                <label class="noFloat" md-no-float="">Your LinkedIn</label>
                                <input name="volunteerLinkedIn" ng-model="model.data.volunteerLinkedIn" placeholder="e.g. linkedin.com/in/george-washington"> </md-input-container>
                        </div>
                    </div>
                    <div class="whiteframePadding" md-whiteframe="2">
                        <md-input-container class="md-input-has-placeholder">
                            <md-select-label class="noFloat" md-no-float="">How many hours can you contribute per week?<span class="required">*</span></md-select-label>
                            <md-select aria-label="Your State" md-no-asterisk="" name="volunteerAvailability" ng-model="model.data.volunteerAvailability" required="true">
                                <md-option ng-repeat="(key, value) in options.dynamicOptions.availability" ng-value="key"> {{ value }} </md-option>
                            </md-select>
                            <div ng-messages="Volunteer.volunteerAvailability.$error" role="alert">
                                <div ng-message-exp="['required']">Please select your availability.</div>
                            </div>
                            <div class="md-errors-spacer"></div>
                        </md-input-container>
                    </div>
                </div>
                <div flex="5"></div>
                <div flex="100" flex-gt-sm="55">
                    <div class="whiteframePadding" md-whiteframe="2">
                        <h2>How Can You Help?</h2>
                        <div layout="column">
                            <div ng-repeat="(key, value) in options.dynamicOptions.skills">
                                <md-checkbox name="volunteerSkills" ng-checked="model.exists('volunteerSkills', key)" ng-click="model.toggle('volunteerSkills', key)">{{ value }}</md-checkbox>
                            </div>
                        </div>
                    </div>
                    <div class="whiteframePadding" md-whiteframe="2">
                        <h2>Anything else we should know about you?</h2>
                        <div layout="column">
                            <md-input-container>
                                <textarea name="volunteerProfile" ng-model="model.data.volunteerProfile" placeholder="" rows="4"></textarea>
                                <p class="hint">Tell us about your work experience or anything else you think you could provide that would help.</p>
                            </md-input-container>
                        </div>
                    </div>
                </div>
            </div>
            <br>
            <div class="submitArea textCenter">
                <button class="btn btnBig formSubmit" type="submit">Let Me Help!</button>
            </div>
        </div>
    </form>
</div>

```