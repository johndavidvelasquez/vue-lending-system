<template>
  <div>
    <CRow>
      <CCol md="8">
        <CCard>
          <CCardHeader>
            <strong>Loan Request Form</strong> 
          </CCardHeader>
          <CCardBody>
            <CForm>
              <h6>Borrower's Information</h6>
              <hr/>
              <CInput
                label="Full Name"
                description="First Name"
                horizontal
              />
              <CInput
                label=" "
                description="Middle Name"
                horizontal
              />
              <CInput
                label=" "
                description="Last Name"
                horizontal
              />
              <CInput
                label="Complete Address"
                description="State/Province"
                horizontal
              />
              <CInput
                label=" "
                description="City/Municipality"
                horizontal
              />
              <CInput
                label=" "
                description="Street Address/Building Name and #"
                horizontal
              />
              <CInput
                label="Birth Date"
                type="date"
                horizontal
              />
              <div class="form-row form-group" :key="name">
                <CCol sm="3">
                  Gender
                </CCol>
                <CCol sm="9" :class="key % 2 === 1 ? 'form-inline' : ''">
                  <CInputRadio
                    v-for="(option, optionIndex) in genderOptions"
                    :key="key + option"
                    :label="option"
                    type="radio"
                    :value="option"
                    :custom="key > 1"
                    :name="`Option 1${key}`"
                    :checked="optionIndex === key"
                    :inline="key % 2 === 1"
                  />
                </CCol>
              </div>
              <CInput
                label="Occupation"
                description="Occupation"
                horizontal
              />
              <CInput
                label="Contact Number"
                description="Contact Number"
                horizontal
              />
              <br>
              <h6>Loan Information</h6>
              <hr/>
             
            </CForm>
          </CCardBody>
          <CCardFooter>
            <CButton type="submit" size="sm" color="primary"><CIcon name="cil-check-circle"/> Submit</CButton>
            <CButton type="reset" size="sm" color="danger"><CIcon name="cil-ban"/> Reset</CButton>
          </CCardFooter>
        </CCard>
      </CCol>
    </CRow>
  </div>
</template>

<script>
export default {
  name: 'Forms',
  data () {
    return {
      selected: [], // Must be an array reference!
      show: true,
      horizontal: { label:'col-3', input:'col-9' },
      options: ['Option 1', 'Option 2', 'Option 3'],
      genderOptions: ['Male', 'Female'],
      selectOptions: [
        'Option 1', 'Option 2', 'Option 3',
        { 
          value: ['some value', 'another value'], 
          label: 'Selected option'
        }
      ],
      selectedOption: ['some value', 'another value'],

      formCollapsed: true,
      checkboxNames: ['Checkboxes', 'Inline Checkboxes',
                      'Checkboxes - custom', 'Inline Checkboxes - custom'],
      radioNames: ['Radios', 'Inline Radios',
                    'Radios - custom', 'Inline Radios - custom']
    }
  },
  methods: {
    validator (val) {
      return val ? val.length >= 4 : false
    }
  }
}
</script>
